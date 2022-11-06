<script>
	let logOut;
</script>

<div>
	<!-- Off-canvas menu for mobile, show/hide based on off-canvas menu state. -->
	<div class="fixed inset-0 flex z-40 md:hidden" role="dialog" aria-modal="true">
		<!--
		Off-canvas menu overlay, show/hide based on off-canvas menu state.
  
		Entering: "transition-opacity ease-linear duration-300"
		  From: "opacity-0"
		  To: "opacity-100"
		Leaving: "transition-opacity ease-linear duration-300"
		  From: "opacity-100"
		  To: "opacity-0"
	  -->
		<div class="fixed inset-0 bg-gray-600 bg-opacity-75" aria-hidden="true" />

		<!--
		Off-canvas menu, show/hide based on off-canvas menu state.
  
		Entering: "transition ease-in-out duration-300 transform"
		  From: "-translate-x-full"
		  To: "translate-x-0"
		Leaving: "transition ease-in-out duration-300 transform"
		  From: "translate-x-0"
		  To: "-translate-x-full"
	  -->
		<div class="relative flex-1 flex flex-col max-w-xs w-full pt-5 pb-4 bg-gray-800">
			<!--
		  Close button, show/hide based on off-canvas menu state.
  
		  Entering: "ease-in-out duration-300"
			From: "opacity-0"
			To: "opacity-100"
		  Leaving: "ease-in-out duration-300"
			From: "opacity-100"
			To: "opacity-0"
		-->
			<div class="absolute top-0 right-0 -mr-12 pt-2">
				<button
					type="button"
					class="ml-1 flex items-center justify-center h-10 w-10 rounded-full focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white"
				>
					<span class="sr-only">Close sidebar</span>
					<!-- Heroicon name: outline/x -->
					<svg
						class="h-6 w-6 text-white"
						xmlns="http://www.w3.org/2000/svg"
						fill="none"
						viewBox="0 0 24 24"
						stroke="currentColor"
						aria-hidden="true"
					>
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M6 18L18 6M6 6l12 12"
						/>
					</svg>
				</button>
			</div>

			<div class="flex-shrink-0 flex items-center px-4">
				<img
					class="h-8 w-auto"
					src="https://tailwindui.com/img/logos/workflow-logo-indigo-500-mark-white-text.svg"
					alt="Workflow"
				/>
			</div>
			<div class="mt-5 flex-1 h-0 overflow-y-auto">
				<nav class="px-2 space-y-1">
					<!-- Current: "bg-gray-900 text-white", Default: "text-gray-300 hover:bg-gray-700 hover:text-white" -->
					<a
						href="/dashboard"
						class="bg-gray-900 text-white group flex items-center px-2 py-2 text-base font-medium rounded-md"
					>
						<!--
				Heroicon name: outline/home
  
				Current: "text-gray-300", Default: "text-gray-400 group-hover:text-gray-300"
			  -->
						<svg
							class="text-gray-300 mr-4 flex-shrink-0 h-6 w-6"
							xmlns="http://www.w3.org/2000/svg"
							fill="none"
							viewBox="0 0 24 24"
							stroke="currentColor"
							aria-hidden="true"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6"
							/>
						</svg>
						Dashboard
					</a>

					<a
						href="#"
						class="text-gray-300 hover:bg-gray-700 hover:text-white group flex items-center px-2 py-2 text-base font-medium rounded-md"
					>
						<!-- Heroicon name: outline/users -->
						<svg
							class="text-gray-400 group-hover:text-gray-300 mr-4 flex-shrink-0 h-6 w-6"
							xmlns="http://www.w3.org/2000/svg"
							fill="none"
							viewBox="0 0 24 24"
							stroke="currentColor"
							aria-hidden="true"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M12 4.354a4 4 0 110 5.292M15 21H3v-1a6 6 0 0112 0v1zm0 0h6v-1a6 6 0 00-9-5.197M13 7a4 4 0 11-8 0 4 4 0 018 0z"
							/>
						</svg>
						Team
					</a>

					<a
						href="packagesmenu"
						class="text-gray-300 hover:bg-gray-700 hover:text-white group flex items-center px-2 py-2 text-base font-medium rounded-md"
					>
						<!-- Heroicon name: outline/folder -->
						<svg
							class="text-gray-400 group-hover:text-gray-300 mr-4 flex-shrink-0 h-6 w-6"
							xmlns="http://www.w3.org/2000/svg"
							fill="none"
							viewBox="0 0 24 24"
							stroke="currentColor"
							aria-hidden="true"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M3 7v10a2 2 0 002 2h14a2 2 0 002-2V9a2 2 0 00-2-2h-6l-2-2H5a2 2 0 00-2 2z"
							/>
						</svg>
						Packages Menu
					</a>

					<a
						href="#"
						class="text-gray-300 hover:bg-gray-700 hover:text-white group flex items-center px-2 py-2 text-base font-medium rounded-md"
					>
						<!-- Heroicon name: outline/calendar -->
						<svg
							class="text-gray-400 group-hover:text-gray-300 mr-4 flex-shrink-0 h-6 w-6"
							xmlns="http://www.w3.org/2000/svg"
							fill="none"
							viewBox="0 0 24 24"
							stroke="currentColor"
							aria-hidden="true"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z"
							/>
						</svg>
						Calendar
					</a>

					<a
						href="#"
						class="text-gray-300 hover:bg-gray-700 hover:text-white group flex items-center px-2 py-2 text-base font-medium rounded-md"
					>
						<!-- Heroicon name: outline/inbox -->
						<svg
							class="text-gray-400 group-hover:text-gray-300 mr-4 flex-shrink-0 h-6 w-6"
							xmlns="http://www.w3.org/2000/svg"
							fill="none"
							viewBox="0 0 24 24"
							stroke="currentColor"
							aria-hidden="true"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M20 13V6a2 2 0 00-2-2H6a2 2 0 00-2 2v7m16 0v5a2 2 0 01-2 2H6a2 2 0 01-2-2v-5m16 0h-2.586a1 1 0 00-.707.293l-2.414 2.414a1 1 0 01-.707.293h-3.172a1 1 0 01-.707-.293l-2.414-2.414A1 1 0 006.586 13H4"
							/>
						</svg>
						Documents
					</a>

					<a
						href="#"
						class="text-gray-300 hover:bg-gray-700 hover:text-white group flex items-center px-2 py-2 text-base font-medium rounded-md"
					>
						<!-- Heroicon name: outline/chart-bar -->
						<svg
							class="text-gray-400 group-hover:text-gray-300 mr-4 flex-shrink-0 h-6 w-6"
							xmlns="http://www.w3.org/2000/svg"
							fill="none"
							viewBox="0 0 24 24"
							stroke="currentColor"
							aria-hidden="true"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z"
							/>
						</svg>
						Reports
					</a>
				</nav>
			</div>
		</div>

		<div class="flex-shrink-0 w-14" aria-hidden="true">
			<!-- Dummy element to force sidebar to shrink to fit close icon -->
		</div>
	</div>

	<!-- Static sidebar for desktop -->
	<div class="hidden md:flex md:w-64 md:flex-col md:fixed md:inset-y-0">
		<!-- Sidebar component, swap this element with another sidebar if you like -->
		<div class="flex-1 flex flex-col min-h-0 bg-gray-800">
			<div class="flex items-center h-16 flex-shrink-0 px-4 bg-gray-900">
				<img
					class="h-8 w-auto"
					src="https://tailwindui.com/img/logos/workflow-logo-indigo-500-mark-white-text.svg"
					alt="Workflow"
				/>
			</div>
			<div class="flex-1 flex flex-col overflow-y-auto">
				<nav class="flex-1 px-2 py-4 space-y-1">
					<!-- Current: "bg-gray-900 text-white", Default: "text-gray-300 hover:bg-gray-700 hover:text-white" -->
					<a
						href="/dashboard"
						class="bg-gray-900 text-white group flex items-center px-2 py-2 text-sm font-medium rounded-md"
					>
						<!--
				Heroicon name: outline/home
  
				Current: "text-gray-300", Default: "text-gray-400 group-hover:text-gray-300"
			  -->
						<svg
							class="text-gray-300 mr-3 flex-shrink-0 h-6 w-6"
							xmlns="http://www.w3.org/2000/svg"
							fill="none"
							viewBox="0 0 24 24"
							stroke="currentColor"
							aria-hidden="true"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6"
							/>
						</svg>
						Dashboard
					</a>

					<a
						href="#"
						class="text-gray-300 hover:bg-gray-700 hover:text-white group flex items-center px-2 py-2 text-sm font-medium rounded-md"
					>
						<!-- Heroicon name: outline/users -->
						<svg
							class="text-gray-400 group-hover:text-gray-300 mr-3 flex-shrink-0 h-6 w-6"
							xmlns="http://www.w3.org/2000/svg"
							fill="none"
							viewBox="0 0 24 24"
							stroke="currentColor"
							aria-hidden="true"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M12 4.354a4 4 0 110 5.292M15 21H3v-1a6 6 0 0112 0v1zm0 0h6v-1a6 6 0 00-9-5.197M13 7a4 4 0 11-8 0 4 4 0 018 0z"
							/>
						</svg>
						Team
					</a>

					<a
						href="packagesmenu"
						class="text-gray-300 hover:bg-gray-700 hover:text-white group flex items-center px-2 py-2 text-sm font-medium rounded-md"
					>
						<!-- Heroicon name: outline/folder -->
						<svg
							class="text-gray-400 group-hover:text-gray-300 mr-3 flex-shrink-0 h-6 w-6"
							xmlns="http://www.w3.org/2000/svg"
							fill="none"
							viewBox="0 0 24 24"
							stroke="currentColor"
							aria-hidden="true"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M3 7v10a2 2 0 002 2h14a2 2 0 002-2V9a2 2 0 00-2-2h-6l-2-2H5a2 2 0 00-2 2z"
							/>
						</svg>
						Packages Menu
					</a>

					<a
						href="#"
						class="text-gray-300 hover:bg-gray-700 hover:text-white group flex items-center px-2 py-2 text-sm font-medium rounded-md"
					>
						<!-- Heroicon name: outline/calendar -->
						<svg
							class="text-gray-400 group-hover:text-gray-300 mr-3 flex-shrink-0 h-6 w-6"
							xmlns="http://www.w3.org/2000/svg"
							fill="none"
							viewBox="0 0 24 24"
							stroke="currentColor"
							aria-hidden="true"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z"
							/>
						</svg>
						Calendar
					</a>

					<a
						href="#"
						class="text-gray-300 hover:bg-gray-700 hover:text-white group flex items-center px-2 py-2 text-sm font-medium rounded-md"
					>
						<!-- Heroicon name: outline/inbox -->
						<svg
							class="text-gray-400 group-hover:text-gray-300 mr-3 flex-shrink-0 h-6 w-6"
							xmlns="http://www.w3.org/2000/svg"
							fill="none"
							viewBox="0 0 24 24"
							stroke="currentColor"
							aria-hidden="true"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M20 13V6a2 2 0 00-2-2H6a2 2 0 00-2 2v7m16 0v5a2 2 0 01-2 2H6a2 2 0 01-2-2v-5m16 0h-2.586a1 1 0 00-.707.293l-2.414 2.414a1 1 0 01-.707.293h-3.172a1 1 0 01-.707-.293l-2.414-2.414A1 1 0 006.586 13H4"
							/>
						</svg>
						Documents
					</a>

					<a
						href="#"
						class="text-gray-300 hover:bg-gray-700 hover:text-white group flex items-center px-2 py-2 text-sm font-medium rounded-md"
					>
						<!-- Heroicon name: outline/chart-bar -->
						<svg
							class="text-gray-400 group-hover:text-gray-300 mr-3 flex-shrink-0 h-6 w-6"
							xmlns="http://www.w3.org/2000/svg"
							fill="none"
							viewBox="0 0 24 24"
							stroke="currentColor"
							aria-hidden="true"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z"
							/>
						</svg>
						Reports
					</a>
				</nav>
			</div>
		</div>
	</div>
	<div class="md:pl-64 flex flex-col">
		<div class="sticky top-0 z-10 flex-shrink-0 flex h-16 bg-white shadow">
			<button
				type="button"
				class="px-4 border-r border-gray-200 text-gray-500 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-indigo-500 md:hidden"
			>
				<span class="sr-only">Open sidebar</span>
				<!-- Heroicon name: outline/menu-alt-2 -->
				<svg
					class="h-6 w-6"
					xmlns="http://www.w3.org/2000/svg"
					fill="none"
					viewBox="0 0 24 24"
					stroke="currentColor"
					aria-hidden="true"
				>
					<path
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="2"
						d="M4 6h16M4 12h16M4 18h7"
					/>
				</svg>
			</button>
			<div class="flex-1 px-4 flex justify-between">
				<div class="flex-1 flex">
					<form class="w-full flex md:ml-0" action="#" method="GET">
						<label for="search-field" class="sr-only">Search</label>
						<div class="relative w-full text-gray-400 focus-within:text-gray-600">
							<div class="absolute inset-y-0 left-0 flex items-center pointer-events-none">
								<!-- Heroicon name: solid/search -->
								<svg
									class="h-5 w-5"
									xmlns="http://www.w3.org/2000/svg"
									viewBox="0 0 20 20"
									fill="currentColor"
									aria-hidden="true"
								>
									<path
										fill-rule="evenodd"
										d="M8 4a4 4 0 100 8 4 4 0 000-8zM2 8a6 6 0 1110.89 3.476l4.817 4.817a1 1 0 01-1.414 1.414l-4.816-4.816A6 6 0 012 8z"
										clip-rule="evenodd"
									/>
								</svg>
							</div>
							<input
								id="search-field"
								class="block w-full h-full pl-8 pr-3 py-2 border-transparent text-gray-900 placeholder-gray-500 focus:outline-none focus:placeholder-gray-400 focus:ring-0 focus:border-transparent sm:text-sm"
								placeholder="Search"
								type="search"
								name="search"
							/>
						</div>
					</form>
				</div>
				<div class="ml-4 flex items-center md:ml-6">
					<button
						type="button"
						class="bg-white p-1 rounded-full text-gray-400 hover:text-gray-500 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
					>
						<span class="sr-only">View notifications</span>
						<!-- Heroicon name: outline/bell -->
						<svg
							class="h-6 w-6"
							xmlns="http://www.w3.org/2000/svg"
							fill="none"
							viewBox="0 0 24 24"
							stroke="currentColor"
							aria-hidden="true"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9"
							/>
						</svg>
					</button>

					<!-- Profile dropdown -->
					<div class="ml-3 relative">
						<div>
							<button
								type="button"
								class="max-w-xs bg-white flex items-center text-sm rounded-full focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
								id="user-menu-button"
								aria-expanded="false"
								aria-haspopup="true"
								on:click={() => (logOut = !logOut)}
							>
								<span class="sr-only">Open user menu</span>
								<img
									class="h-8 w-8 rounded-full"
									src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80"
									alt=""
								/>
							</button>
						</div>

						<!--
				Dropdown menu, show/hide based on menu state.
  
				Entering: "transition ease-out duration-100"
				  From: "transform opacity-0 scale-95"
				  To: "transform opacity-100 scale-100"
				Leaving: "transition ease-in duration-75"
				  From: "transform opacity-100 scale-100"
				  To: "transform opacity-0 scale-95"
			  -->
						<div
							class="origin-top-right absolute right-0 mt-2 w-48 rounded-md shadow-lg py-1 bg-white ring-1 ring-black ring-opacity-5 focus:outline-none"
							role="menu"
							aria-orientation="vertical"
							aria-labelledby="user-menu-button"
							tabindex="-1"
							style:visibility={logOut ? 'visible' : 'hidden'}
						>
							<!-- Active: "bg-gray-100", Not Active: "" -->
							<a
								href="#"
								class="block px-4 py-2 text-sm text-gray-700"
								role="menuitem"
								tabindex="-1"
								id="user-menu-item-0">Your Profile</a
							>

							<a
								href="#"
								class="block px-4 py-2 text-sm text-gray-700"
								role="menuitem"
								tabindex="-1"
								id="user-menu-item-1">Settings</a
							>

							<a
								href="/"
								class="block px-4 py-2 text-sm text-gray-700"
								role="menuitem"
								tabindex="-1"
								id="user-menu-item-2">Sign out</a
							>
						</div>
					</div>
				</div>
			</div>
		</div>

		<main class="flex-1">
			<div class="py-6">
				<div class="max-w-7xl mx-auto px-4 sm:px-6 md:px-8">
					<h1 class="text-2xl font-semibold text-gray-900">Dashboard</h1>
				</div>
				<div class="max-w-7xl mx-auto px-4 sm:px-6 md:px-8">
					<!-- Replace with your content -->
					<!-- This example requires Tailwind CSS v2.0+ -->
					<div class="md:grid md:grid-cols-2 md:divide-x md:divide-gray-200">
						<div class="md:pr-14">
							<div class="flex items-center">
								<h2 class="flex-auto font-semibold text-gray-900">January 2022</h2>
								<button
									type="button"
									class="-my-1.5 flex flex-none items-center justify-center p-1.5 text-gray-400 hover:text-gray-500"
								>
									<span class="sr-only">Previous month</span>
									<!-- Heroicon name: solid/chevron-left -->
									<svg
										class="h-5 w-5"
										xmlns="http://www.w3.org/2000/svg"
										viewBox="0 0 20 20"
										fill="currentColor"
										aria-hidden="true"
									>
										<path
											fill-rule="evenodd"
											d="M12.707 5.293a1 1 0 010 1.414L9.414 10l3.293 3.293a1 1 0 01-1.414 1.414l-4-4a1 1 0 010-1.414l4-4a1 1 0 011.414 0z"
											clip-rule="evenodd"
										/>
									</svg>
								</button>
								<button
									type="button"
									class="-my-1.5 -mr-1.5 ml-2 flex flex-none items-center justify-center p-1.5 text-gray-400 hover:text-gray-500"
								>
									<span class="sr-only">Next month</span>
									<!-- Heroicon name: solid/chevron-right -->
									<svg
										class="h-5 w-5"
										xmlns="http://www.w3.org/2000/svg"
										viewBox="0 0 20 20"
										fill="currentColor"
										aria-hidden="true"
									>
										<path
											fill-rule="evenodd"
											d="M7.293 14.707a1 1 0 010-1.414L10.586 10 7.293 6.707a1 1 0 011.414-1.414l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414 0z"
											clip-rule="evenodd"
										/>
									</svg>
								</button>
							</div>
							<div class="mt-10 grid grid-cols-7 text-center text-xs leading-6 text-gray-500">
								<div>M</div>
								<div>T</div>
								<div>W</div>
								<div>T</div>
								<div>F</div>
								<div>S</div>
								<div>S</div>
							</div>
							<div class="mt-2 grid grid-cols-7 text-sm">
								<div class="py-2">
									<!--
			Always include: "mx-auto flex h-8 w-8 items-center justify-center rounded-full"
			Is selected, include: "text-white"
			Is not selected and is today, include: "text-indigo-600"
			Is not selected and is not today and is current month, include: "text-gray-900"
			Is not selected and is not today and is not current month, include: "text-gray-400"
			Is selected and is today, include: "bg-indigo-600"
			Is selected and is not today, include: "bg-gray-900"
			Is not selected, include: "hover:bg-gray-200"
			Is selected or is today, include: "font-semibold"
		  -->
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-400 hover:bg-gray-200"
									>
										<time datetime="2021-12-27">27</time>
									</button>
								</div>
								<div class="py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-400 hover:bg-gray-200"
									>
										<time datetime="2021-12-28">28</time>
									</button>
								</div>
								<div class="py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-400 hover:bg-gray-200"
									>
										<time datetime="2021-12-29">29</time>
									</button>
								</div>
								<div class="py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-400 hover:bg-gray-200"
									>
										<time datetime="2021-12-30">30</time>
									</button>
								</div>
								<div class="py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-400 hover:bg-gray-200"
									>
										<time datetime="2021-12-31">31</time>
									</button>
								</div>
								<div class="py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-900 hover:bg-gray-200"
									>
										<time datetime="2022-01-01">1</time>
									</button>
								</div>
								<div class="py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-900 hover:bg-gray-200"
									>
										<time datetime="2022-01-02">2</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-900 hover:bg-gray-200"
									>
										<time datetime="2022-01-03">3</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-900 hover:bg-gray-200"
									>
										<time datetime="2022-01-04">4</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-900 hover:bg-gray-200"
									>
										<time datetime="2022-01-05">5</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-900 hover:bg-gray-200"
									>
										<time datetime="2022-01-06">6</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-900 hover:bg-gray-200"
									>
										<time datetime="2022-01-07">7</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-900 hover:bg-gray-200"
									>
										<time datetime="2022-01-08">8</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-900 hover:bg-gray-200"
									>
										<time datetime="2022-01-09">9</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-900 hover:bg-gray-200"
									>
										<time datetime="2022-01-10">10</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-900 hover:bg-gray-200"
									>
										<time datetime="2022-01-11">11</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full font-semibold text-indigo-600 hover:bg-gray-200"
									>
										<time datetime="2022-01-12">12</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-900 hover:bg-gray-200"
									>
										<time datetime="2022-01-13">13</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-900 hover:bg-gray-200"
									>
										<time datetime="2022-01-14">14</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-900 hover:bg-gray-200"
									>
										<time datetime="2022-01-15">15</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-900 hover:bg-gray-200"
									>
										<time datetime="2022-01-16">16</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-900 hover:bg-gray-200"
									>
										<time datetime="2022-01-17">17</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-900 hover:bg-gray-200"
									>
										<time datetime="2022-01-18">18</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-900 hover:bg-gray-200"
									>
										<time datetime="2022-01-19">19</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-900 hover:bg-gray-200"
									>
										<time datetime="2022-01-20">20</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full bg-gray-900 font-semibold text-white"
									>
										<time datetime="2022-01-21">21</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-900 hover:bg-gray-200"
									>
										<time datetime="2022-01-22">22</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-900 hover:bg-gray-200"
									>
										<time datetime="2022-01-23">23</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-900 hover:bg-gray-200"
									>
										<time datetime="2022-01-24">24</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-900 hover:bg-gray-200"
									>
										<time datetime="2022-01-25">25</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-900 hover:bg-gray-200"
									>
										<time datetime="2022-01-26">26</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-900 hover:bg-gray-200"
									>
										<time datetime="2022-01-27">27</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-900 hover:bg-gray-200"
									>
										<time datetime="2022-01-28">28</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-900 hover:bg-gray-200"
									>
										<time datetime="2022-01-29">29</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-900 hover:bg-gray-200"
									>
										<time datetime="2022-01-30">30</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-900 hover:bg-gray-200"
									>
										<time datetime="2022-01-31">31</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-400 hover:bg-gray-200"
									>
										<time datetime="2022-02-01">1</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-400 hover:bg-gray-200"
									>
										<time datetime="2022-02-02">2</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-400 hover:bg-gray-200"
									>
										<time datetime="2022-02-03">3</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-400 hover:bg-gray-200"
									>
										<time datetime="2022-02-04">4</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-400 hover:bg-gray-200"
									>
										<time datetime="2022-02-05">5</time>
									</button>
								</div>
								<div class="border-t border-gray-200 py-2">
									<button
										type="button"
										class="mx-auto flex h-8 w-8 items-center justify-center rounded-full text-gray-400 hover:bg-gray-200"
									>
										<time datetime="2022-02-06">6</time>
									</button>
								</div>
							</div>
						</div>
						<section class="mt-12 md:mt-0 md:pl-14">
							<h2 class="font-semibold text-gray-900">
								Schedule for <time datetime="2022-01-21">January 21, 2022</time>
							</h2>
							<ol class="mt-4 space-y-1 text-sm leading-6 text-gray-500">
								<li
									class="group flex items-center space-x-4 rounded-xl py-2 px-4 focus-within:bg-gray-100 hover:bg-gray-100"
								>
									<img
										src="https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80"
										alt=""
										class="h-10 w-10 flex-none rounded-full"
									/>
									<div class="flex-auto">
										<p class="text-gray-900">Leslie Alexander</p>
										<p class="mt-0.5">
											<time datetime="2022-01-21T13:00">1:00 PM</time> -
											<time datetime="2022-01-21T14:30">2:30 PM</time>
										</p>
									</div>
									<div class="relative opacity-0 focus-within:opacity-100 group-hover:opacity-100">
										<div>
											<button
												type="button"
												class="-m-2 flex items-center rounded-full p-1.5 text-gray-500 hover:text-gray-600"
												id="menu-0-button"
												aria-expanded="false"
												aria-haspopup="true"
											>
												<span class="sr-only">Open options</span>
												<!-- Heroicon name: outline/dots-vertical -->
												<svg
													class="h-6 w-6"
													xmlns="http://www.w3.org/2000/svg"
													fill="none"
													viewBox="0 0 24 24"
													stroke="currentColor"
													aria-hidden="true"
												>
													<path
														stroke-linecap="round"
														stroke-linejoin="round"
														stroke-width="2"
														d="M12 5v.01M12 12v.01M12 19v.01M12 6a1 1 0 110-2 1 1 0 010 2zm0 7a1 1 0 110-2 1 1 0 010 2zm0 7a1 1 0 110-2 1 1 0 010 2z"
													/>
												</svg>
											</button>
										</div>

										<!--
			  Dropdown menu, show/hide based on menu state.
  
			  Entering: "transition ease-out duration-100"
				From: "transform opacity-0 scale-95"
				To: "transform opacity-100 scale-100"
			  Leaving: "transition ease-in duration-75"
				From: "transform opacity-100 scale-100"
				To: "transform opacity-0 scale-95"
			-->
										<div
											class="focus:outline-none absolute right-0 z-10 mt-2 w-36 origin-top-right rounded-md bg-white shadow-lg ring-1 ring-black ring-opacity-5"
											role="menu"
											aria-orientation="vertical"
											aria-labelledby="menu-0-button"
											tabindex="-1"
										>
											<div class="py-1" role="none">
												<!-- Active: "bg-gray-100 text-gray-900", Not Active: "text-gray-700" -->
												<a
													href="#"
													class="text-gray-700 block px-4 py-2 text-sm"
													role="menuitem"
													tabindex="-1"
													id="menu-0-item-0">Edit</a
												>
												<a
													href="#"
													class="text-gray-700 block px-4 py-2 text-sm"
													role="menuitem"
													tabindex="-1"
													id="menu-0-item-1">Cancel</a
												>
											</div>
										</div>
									</div>
								</li>

								<!-- More meetings... -->
							</ol>
						</section>
					</div>

					<!-- /End replace -->
				</div>
			</div>
		</main>
	</div>
</div>
