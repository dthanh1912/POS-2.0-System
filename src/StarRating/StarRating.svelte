<script>
	import { fade, slide } from 'svelte/transition';
	import Star from './Star.svelte';

	// User rating states
	let rating = null;
	let hoverRating = null;

	// form interaction states
	let collectFeedback = false;
	let feedbackCompleted = false;

	// "$:" triggers when something in the line changes
	// When these variables reach true/false, they trigger these functions
	$: collectFeedback && addWatchListeners();
	$: !collectFeedback && feedbackFormClosed();

	function feedbackFormClosed() {
		feedbackCompleted = false;
		removeWatchListeners();
	}

	function addWatchListeners() {
		document.addEventListener('keydown', userDismissFeedback);
		document.addEventListener('click', userClickedOutsideOfFeedback);
	}
	function removeWatchListeners() {
		document.removeEventListener('keydown', userDismissFeedback);
		document.removeEventListener('click', userClickedOutsideOfFeedback);
	}
	function userClickedOutsideOfFeedback(event) {
		const container = document.getElementById('feedbackContiner');
		if (!container.contains(event.target)) {
			collectFeedback = false;
		}
	}
	function userDismissFeedback(event) {
		switch (event.key) {
			case 'Escape':
				collectFeedback = false;
				break;
			default:
				return;
		}
	}

	// using curried function to initialize hover with id
	const handleHover = (id) => () => {
		hoverRating = id;
	};
	const handleRate = (id) => (event) => {
		if (
			collectFeedback &&
			rating &&
			rating.toString() === event.srcElement.dataset.starid
		) {
			collectFeedback = false;
			return;
		}
		rating = id;
		collectFeedback = true;
	};

	let stars = [
		{ id: 1, title: 'One Star' },
		{ id: 2, title: 'Two Stars' },
		{ id: 3, title: 'Three Stars' },
		{ id: 4, title: 'Four Stars' },
		{ id: 5, title: 'Five Stars' },
	];

	function handleCollectFeedback(e) {
		// let them know we recieved it
		feedbackCompleted = true;

		// then reset view
		setTimeout(() => {
			collectFeedback = false;
			feedbackCompleted = false;
		}, 1250);
	}
</script>

<div class="feedback">
	<span
		id="feedbackContiner"
		class="feedbackContainer"
		class:feedbackContainerDisabled={feedbackCompleted}
	>
		<span class="starContainer">
			{#each stars as star (star.id)}
				<Star
					filled={hoverRating
						? hoverRating >= star.id
						: rating >= star.id}
					starId={star.id}
					on:mouseover={handleHover(star.id)}
					on:mouseleave={() => (hoverRating = null)}
					on:click={handleRate(star.id)}
				/>
			{/each}
		</span>
		<br />
		<!-- {#if collectFeedback}
      <div class="collectFeedbackContainer" transition:fade>
        {#if feedbackCompleted}
          <p>Thank you!</p>
        {:else}
          <form
            on:submit|preventDefault={handleCollectFeedback}
            transition:slide={{ duration: 450 }}
          >
            <p>
              You've selected {rating ? rating : "no"} star{rating === 1
                ? ""
                : "s"},
              <br />
              please tell us why you gave us this rating
            </p>
            <textarea />
            <button> Send Feedback </button>
            <button
              on:click={() => (collectFeedback = false)}
              type="button"
              class="cancel"
            >
              No Thanks
            </button>
          </form>
        {/if} -->
		<!-- </div>
    {/if} -->
	</span>
</div>

<style>
	.feedback {
		position: relative;
	}
	/* .collectFeedbackContainer {
    width: 300px;
    position: absolute;
    top: 44px;
    left: 0;
    background: #fff;
    border: 1px solid #666;
    padding: 8px;
    transition: transform 0.2s ease-out;
  }
  .collectFeedbackContainer textarea {
    display: block;
    width: 100%;
    height: 120px;
    resize: none;
  }
  .cancel {
    background: none;
    text-decoration: underline;
    border: none;
  } */
	.starContainer {
		display: inline-block;
		transition: background 0.2s ease-out;
		border-radius: 8px;
		padding: 4px 6px 0;
	}
	.feedbackContainerDisabled {
		pointer-events: none;
	}
	@media only screen and (max-width: 767px) {
    .starContainer {
      display: flex;
      align-items: center;
      justify-content: center;
    }
	}
	:global(button) {
		cursor: pointer;
	}
</style>
