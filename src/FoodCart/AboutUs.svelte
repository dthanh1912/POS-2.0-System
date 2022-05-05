<div class="container">
	<div class="introduction">
		<h2>Who are we? Meet our team!</h2>
		We listen, we discuss and we develop. We love to learn and use the lastest
		technologies.
	</div>
	<div class="team-member">
		<div class="member-card">
			<img
				class="member-card-image"
				src={`img/khoi.jpeg`}
				alt="khoi.jpeg"
			/>
			<div class="member-card-name">Le Minh Khoi</div>
			<div class="member-card-info">Developer</div>
		</div>
		<div class="member-card">
			<img
				class="member-card-image"
				src={`img/viet.jpeg`}
				alt="viet.jpeg"
			/>
			<div class="member-card-name">Tran Quoc Viet</div>
			<div class="member-card-info">Developer</div>
		</div>
		<div class="member-card">
			<img
				class="member-card-image"
				src={`img/tam.jpeg`}
				alt="tam.jpeg"
			/>
			<div class="member-card-name">Nguyen Minh Tam</div>
			<div class="member-card-info">Developer</div>
		</div>
		<div class="member-card">
			<img
				class="member-card-image"
				src={`img/thanh.jpeg`}
				alt="thanh.jpeg"
			/>
			<div class="member-card-name">Nguyen Duc Thanh</div>
			<div class="member-card-info">Developer</div>
		</div>
	</div>
	<div class="footer">
		<div class="text">
			<hr />
			<h3 style="text-align: center">Special thanks to</h3>
		</div>
		<div class="credit-small">
			<div class="contributor-card">
				<img
					class="contributor-card-image"
					src={`img/d1.jpg`}
					alt="d1.jpeg"
				/>
				<h5>Dr. Nguyen Duc Anh</h5>
			</div>
			<div class="contributor-card">
				<h5>&</h5>
			</div>
			<div class="contributor-card">
				<img
					class="contributor-card-image"
					src={`img/d2.jpg`}
					alt="d2.jpeg"
				/>
				<h5>Dr. Quan Thanh Tho</h5>
			</div>
		</div>
		<h4 style="text-align: center">
			For always guiding and assisting us in completing this project
		</h4>
	</div>
	<div class="footer">
		<div class="text">
			<hr />
			<h3>References</h3>
		</div>
		<div class="credit">
			<div class="contributor-card">
				<img
					class="contributor-card-image"
					src={`img/g1.jpeg`}
					alt="contributor1.jpeg"
				/>
				<div class="contributor-info">
					<h5>Deven Rathore</h5>
					<h6>
						Thank you for giving us a base source code of this
						project
					</h6>
					<a href="https://github.com/Dunebook/SvelteEcommercecart"
						>Github link</a
					>
				</div>
			</div>
			<div class="contributor-card">
				<img
					class="contributor-card-image"
					src={`img/g2.jpeg`}
					alt="contributor2.jpeg"
				/>
				<div class="contributor-info">
					<h5>Muhammed Erdem</h5>
					<h6>
						Thank you for a gorgeous interactive paycard &#160;
						&#160; &#160;
					</h6>
					<a
						href="https://github.com/muhammed/vue-interactive-paycard"
						>Github link</a
					>
				</div>
			</div>
		</div>
	</div>
</div>

<style>
	.introduction {
		text-align: center;
		width: 100%;
		background: linear-gradient(rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6)),
			url('https://i1.wp.com/wanderin.dev/wp-content/uploads/2019/12/crop-0-0-1170-390-0-about-cover.png?fit=1170%2C390&ssl=1')
				center;
		background-size: cover;
		background-repeat: no-repeat;
		height: 400px;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		color: white;
		padding: 20px;
	}
	.credit {
		text-align: center;
		display: flex;
		align-items: center;
		justify-content: space-between;
		margin: 50px 0px;
	}
	.credit-small {
		text-align: center;
		display: flex;
		align-items: center;
		justify-content: center;
		gap: 3%;
		margin: 50px 0px;
	}
	.footer {
		transform: translateY(-120px);
		width: 100%;
		height: auto;
	}
	.contributor-card {
		display: flex;
		align-items: center;
		justify-content: flex-start;
		gap: 25px;
	}
	.team-member {
		width: 100%;
		height: 300px;
		transform: translateY(-120px);
		display: flex;
		align-items: center;
		justify-content: space-around;
		flex-wrap: wrap;
		position: relative;
	}
	.member-card {
		width: 25%;
		height: 300px;
		display: flex;
		align-items: center;
		justify-content: center;
		flex-direction: column;
		gap: 10px;
	}
	.member-card-image {
		width: 180px;
		height: 180px;
		border-radius: 50%;
	}
	@media only screen and (max-width: 767px) {
		.member-card {
			width: 60%;
		}
		.footer {
			transform: translateY(750px);
		}
		.credit {
			flex-direction: column;
			gap: 40px;
			justify-content: flex-start;
			align-items: flex-start;
		}
		.credit-small {
			flex-direction: column;
			gap: 10px;
			justify-content: center;
			align-items: center;
		}
	}
	.member-card-name {
		font-weight: bold;
		letter-spacing: 1px;
	}
	.contributor-card-image {
		width: 100px;
		height: 100px;
		border-radius: 50%;
	}
	.contributor-info {
		text-align: left;
	}
</style>
