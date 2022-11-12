<script>
	import logo from '$lib/image/logosnpmpc.png';
	import pic1 from '$lib/image/signinpic.jpg';
</script>

<div class="min-h-screen flex">
	<div
		class="flex-1 flex flex-col justify-center py-12 px-4 sm:px-6 lg:flex-none lg:px-20 xl:px-24 bg-gray-800"
	>
		<div class="mx-auto w-full max-w-sm lg:w-96">
			<div>
				<img class="h-20 w-auto mx-auto" src={logo} alt="Workflow" />
				<h2 class="text-2xl font-normal text-gray-500">SNPMPC Admin</h2>
			</div>

			<div class="mt-8">
				<div class="mt-6">
					<form action="" method="POST" class="space-y-6">
						<div>
							<label for="email" class="block text-sm font-medium text-gray-300"> Username </label>
							<div class="mt-1">
								<input
									id="email"
									name="email"
									type="email"
									placeholder="Enter Username"
									autocomplete="email"
									required
									class="appearance-none block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm placeholder-gray-400 focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
								/>
							</div>
						</div>

						<div class="space-y-1">
							<label for="password" class="block text-sm font-medium text-gray-300">
								Password
							</label>
							<div class="mt-1">
								<input
									id="password"
									name="password"
									type="password"
									placeholder="Enter Password"
									autocomplete="current-password"
									required
									class="appearance-none block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm placeholder-gray-400 focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
								/>
							</div>
						</div>

						<div>
							<!-- <button
								type="submit"
								class="w-full flex justify-center py-2 px-4 border border-transparent rounded-md shadow-sm text-sm font-medium text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
								>Sign in
                            </button> -->
							<a
								href="/dashboard"
								class="w-full flex justify-center py-2 px-4 border border-transparent rounded-md shadow-sm text-sm font-medium text-white bg-gray-700 hover:bg-gray-900 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
								>Sign in</a
							>
						</div>
					</form>
				</div>
			</div>
		</div>
	</div>
	<div class="hidden lg:block relative w-0 flex-1">
		<img class="absolute inset-0 h-full w-full object-cover" src={pic1} alt="Workflow" />
	</div>
</div>
