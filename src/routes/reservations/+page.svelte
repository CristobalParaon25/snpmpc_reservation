<script>
	let isClick = false;
	let options = false;
</script>

<div class="min-h-full">
	<!-- Off-canvas menu for mobile, show/hide based on off-canvas menu state. -->
	<div class="fixed inset-0 flex z-40 lg:hidden" role="dialog" aria-modal="true">
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
		<div class="relative flex-1 flex flex-col max-w-xs w-full pt-5 pb-4 bg-white">
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
					src="https://tailwindui.com/img/logos/workflow-logo-purple-500-mark-gray-700-text.svg"
					alt="Workflow"
				/>
			</div>
			<div class="mt-5 flex-1 h-0 overflow-y-auto">
				<nav class="px-2">
					<div class="space-y-1">
						<!-- Current: "bg-gray-100 text-gray-900", Default: "text-gray-600 hover:text-gray-900 hover:bg-gray-50" -->
						<a
							href="/dashboard"
							class="bg-gray-100 text-gray-900 group flex items-center px-2 py-2 text-base leading-5 font-medium rounded-md"
							aria-current="page"
						>
							<!--
                  Heroicon name: outline/home
  
                  Current: "text-gray-500", Default: "text-gray-400 group-hover:text-gray-500"
                -->
							<svg
								class="text-gray-500 mr-3 flex-shrink-0 h-6 w-6"
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
							Home
						</a>

						<a
							href="#"
							class="text-gray-600 hover:text-gray-900 hover:bg-gray-50 group flex items-center px-2 py-2 text-base leading-5 font-medium rounded-md"
						>
							<!-- Heroicon name: outline/view-list -->
							<svg
								class="text-gray-400 group-hover:text-gray-500 mr-3 flex-shrink-0 h-6 w-6"
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
									d="M4 6h16M4 10h16M4 14h16M4 18h16"
								/>
							</svg>
							Reservations
						</a>

						<a
							href="#"
							class="text-gray-600 hover:text-gray-900 hover:bg-gray-50 group flex items-center px-2 py-2 text-base leading-5 font-medium rounded-md"
						>
							<!-- Heroicon name: outline/clock -->
							<svg
								class="text-gray-400 group-hover:text-gray-500 mr-3 flex-shrink-0 h-6 w-6"
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
									d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"
								/>
							</svg>
							Reports
						</a>
					</div>
				</nav>
			</div>
		</div>

		<div class="flex-shrink-0 w-14" aria-hidden="true">
			<!-- Dummy element to force sidebar to shrink to fit close icon -->
		</div>
	</div>

	<!-- Static sidebar for desktop -->
	<div
		class="hidden lg:flex lg:flex-col lg:w-64 lg:fixed lg:inset-y-0 lg:border-r lg:border-gray-200 lg:pt-5 lg:pb-4 lg:bg-gray-100"
	>
		<div class="flex items-center flex-shrink-0 px-6">
			<img
				class="h-8 w-auto"
				src="https://tailwindui.com/img/logos/workflow-logo-purple-500-mark-gray-700-text.svg"
				alt="Workflow"
			/>
		</div>
		<!-- Sidebar component, swap this element with another sidebar if you like -->
		<div class="mt-6 h-0 flex-1 flex flex-col overflow-y-auto pt-3">
			<!-- User account dropdown -->
			<div class="px-3 relative inline-block text-left">
				<div>
					<button
						type="button"
						class="group w-full bg-gray-100 rounded-md px-3.5 py-2 text-sm text-left font-medium text-gray-700 hover:bg-gray-200 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-offset-gray-100 focus:ring-purple-500"
						id="options-menu-button"
						aria-expanded="false"
						aria-haspopup="true"
						on:click={() => (isClick = !isClick)}
					>
						<span class="flex w-full justify-between items-center">
							<span class="flex min-w-0 items-center justify-between space-x-3">
								<img
									class="w-10 h-10 bg-gray-300 rounded-full flex-shrink-0"
									src="https://images.unsplash.com/photo-1502685104226-ee32379fefbe?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=3&w=256&h=256&q=80"
									alt=""
								/>
								<span class="flex-1 flex flex-col min-w-0">
									<span class="text-gray-900 text-sm font-medium truncate">Jessy Schwarz</span>
									<span class="text-gray-500 text-sm truncate">@jessyschwarz</span>
								</span>
							</span>
							<!-- Heroicon name: solid/selector -->
							<svg
								class="flex-shrink-0 h-5 w-5 text-gray-400 group-hover:text-gray-500"
								xmlns="http://www.w3.org/2000/svg"
								viewBox="0 0 20 20"
								fill="currentColor"
								aria-hidden="true"
							>
								<path
									fill-rule="evenodd"
									d="M10 3a1 1 0 01.707.293l3 3a1 1 0 01-1.414 1.414L10 5.414 7.707 7.707a1 1 0 01-1.414-1.414l3-3A1 1 0 0110 3zm-3.707 9.293a1 1 0 011.414 0L10 14.586l2.293-2.293a1 1 0 011.414 1.414l-3 3a1 1 0 01-1.414 0l-3-3a1 1 0 010-1.414z"
									clip-rule="evenodd"
								/>
							</svg>
						</span>
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
					class="z-10 mx-3 origin-top absolute right-0 left-0 mt-1 rounded-md shadow-lg bg-white ring-1 ring-black 
                    ring-opacity-5 divide-y divide-gray-200 focus:outline-none"
					style:visibility={isClick ? 'visible' : 'hidden'}
					role="menu"
					aria-orientation="vertical"
					aria-labelledby="options-menu-button"
					tabindex="-1"
				>
					<div class="py-1" role="none">
						<!-- Active: "bg-gray-100 text-gray-900", Not Active: "text-gray-700" -->
						<a
							href="#"
							class="text-gray-700 block px-4 py-2 text-sm"
							role="menuitem"
							tabindex="-1"
							id="options-menu-item-0">View profile</a
						>
						<a
							href="#"
							class="text-gray-700 block px-4 py-2 text-sm"
							role="menuitem"
							tabindex="-1"
							id="options-menu-item-1">Settings</a
						>
						<a
							href="#"
							class="text-gray-700 block px-4 py-2 text-sm"
							role="menuitem"
							tabindex="-1"
							id="options-menu-item-2">Notifications</a
						>
					</div>
					<div class="py-1" role="none">
						<a
							href="#"
							class="text-gray-700 block px-4 py-2 text-sm"
							role="menuitem"
							tabindex="-1"
							id="options-menu-item-3">Get desktop app</a
						>
						<a
							href="#"
							class="text-gray-700 block px-4 py-2 text-sm"
							role="menuitem"
							tabindex="-1"
							id="options-menu-item-4">Support</a
						>
					</div>
					<div class="py-1" role="none">
						<a
							href="/"
							class="text-gray-700 block px-4 py-2 text-sm"
							role="menuitem"
							tabindex="-1"
							id="options-menu-item-5">Logout</a
						>
					</div>
				</div>
			</div>
			<!-- Sidebar Search -->
			<div class="px-3 mt-5">
				<label for="search" class="sr-only">Search</label>
				<div class="mt-1 relative rounded-md shadow-sm">
					<div
						class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none"
						aria-hidden="true"
					>
						<!-- Heroicon name: solid/search -->
						<svg
							class="mr-3 h-4 w-4 text-gray-400"
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
						type="text"
						name="search"
						id="search"
						class="focus:ring-indigo-500 focus:border-indigo-500 block w-full pl-9 sm:text-sm border-gray-300 rounded-md"
						placeholder="Search"
					/>
				</div>
			</div>
			<!-- Navigation -->
			<nav class="px-3 mt-6">
				<div class="space-y-1">
					<!-- Current: "bg-gray-200 text-gray-900", Default: "text-gray-700 hover:text-gray-900 hover:bg-gray-50" -->
					<a
						href="/dashboard"
						class="bg-gray-200 text-gray-900 group flex items-center px-2 py-2 text-sm font-medium rounded-md"
						aria-current="page"
					>
						<!--
                Heroicon name: outline/home
  
                Current: "text-gray-500", Default: "text-gray-400 group-hover:text-gray-500"
              -->
						<svg
							class="text-gray-500 mr-3 flex-shrink-0 h-6 w-6"
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
						Home
					</a>

					<a
						href="#"
						class="text-gray-700 hover:text-gray-900 hover:bg-gray-50 group flex items-center px-2 py-2 text-sm font-medium rounded-md"
					>
						<!-- Heroicon name: outline/view-list -->
						<svg
							class="text-gray-400 group-hover:text-gray-500 mr-3 flex-shrink-0 h-6 w-6"
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
								d="M4 6h16M4 10h16M4 14h16M4 18h16"
							/>
						</svg>
						Reservations
					</a>

					<a
						href="#"
						class="text-gray-700 hover:text-gray-900 hover:bg-gray-50 group flex items-center px-2 py-2 text-sm font-medium rounded-md"
					>
						<!-- Heroicon name: outline/clock -->
						<svg
							class="text-gray-400 group-hover:text-gray-500 mr-3 flex-shrink-0 h-6 w-6"
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
								d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"
							/>
						</svg>
						Reports
					</a>
				</div>
			</nav>
		</div>
	</div>
	<!-- Main column -->
	<div class="lg:pl-64 flex flex-col">
		<!-- Search header -->
		<div
			class="sticky top-0 z-10 flex-shrink-0 flex h-16 bg-white border-b border-gray-200 lg:hidden"
		>
			<!-- Sidebar toggle, controls the 'sidebarOpen' sidebar state. -->
			<button
				type="button"
				class="px-4 border-r border-gray-200 text-gray-500 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-purple-500 lg:hidden"
			>
				<span class="sr-only">Open sidebar</span>
				<!-- Heroicon name: outline/menu-alt-1 -->
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
						d="M4 6h16M4 12h8m-8 6h16"
					/>
				</svg>
			</button>
			<div class="flex-1 flex justify-between px-4 sm:px-6 lg:px-8">
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
								name="search-field"
								class="block w-full h-full pl-8 pr-3 py-2 border-transparent text-gray-900 placeholder-gray-500 focus:outline-none focus:ring-0 focus:border-transparent focus:placeholder-gray-400 sm:text-sm"
								placeholder="Search"
								type="search"
							/>
						</div>
					</form>
				</div>
				<div class="flex items-center">
					<!-- Profile dropdown -->
					<div class="ml-3 relative">
						<div>
							<button
								type="button"
								class="max-w-xs bg-white flex items-center text-sm rounded-full focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-purple-500"
								id="user-menu-button"
								aria-expanded="false"
								aria-haspopup="true"
							>
								<span class="sr-only">Open user menu</span>
								<img
									class="h-8 w-8 rounded-full"
									src="https://images.unsplash.com/photo-1502685104226-ee32379fefbe?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80"
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
							class="origin-top-right absolute right-0 mt-2 w-48 rounded-md shadow-lg bg-white ring-1 ring-black ring-opacity-5 divide-y divide-gray-200 focus:outline-none"
							role="menu"
							aria-orientation="vertical"
							aria-labelledby="user-menu-button"
							tabindex="-1"
						>
							<div class="py-1" role="none">
								<!-- Active: "bg-gray-100 text-gray-900", Not Active: "text-gray-700" -->
								<a
									href="#"
									class="text-gray-700 block px-4 py-2 text-sm"
									role="menuitem"
									tabindex="-1"
									id="user-menu-item-0">View profile</a
								>
								<a
									href="#"
									class="text-gray-700 block px-4 py-2 text-sm"
									role="menuitem"
									tabindex="-1"
									id="user-menu-item-1">Settings</a
								>
								<a
									href="#"
									class="text-gray-700 block px-4 py-2 text-sm"
									role="menuitem"
									tabindex="-1"
									id="user-menu-item-2">Notifications</a
								>
							</div>
							<div class="py-1" role="none">
								<a
									href="#"
									class="text-gray-700 block px-4 py-2 text-sm"
									role="menuitem"
									tabindex="-1"
									id="user-menu-item-3">Get desktop app</a
								>
								<a
									href="#"
									class="text-gray-700 block px-4 py-2 text-sm"
									role="menuitem"
									tabindex="-1"
									id="user-menu-item-4">Support</a
								>
							</div>
							<div class="py-1" role="none">
								<a
									href="/"
									class="text-gray-700 block px-4 py-2 text-sm"
									role="menuitem"
									tabindex="-1"
									id="user-menu-item-5">Logout</a
								>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
		<main class="flex-1">
			<!-- Page title & actions -->
			<div
				class="border-b border-gray-200 px-4 py-4 sm:flex sm:items-center sm:justify-between sm:px-6 lg:px-8"
			>
				<div class="flex-1 min-w-0">
					<h1 class="text-lg font-medium leading-6 text-gray-900 sm:truncate">Home</h1>
				</div>
				<div class="mt-4 flex sm:mt-0 sm:ml-4">
					<button
						type="button"
						class="order-1 ml-3 inline-flex items-center px-4 py-2 border border-gray-300 shadow-sm text-sm font-medium rounded-md text-gray-700 bg-white hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-purple-500 sm:order-0 sm:ml-0"
						>Share</button
					>
					<button
						type="button"
						class="order-0 inline-flex items-center px-4 py-2 border border-transparent shadow-sm text-sm font-medium rounded-md text-white bg-purple-600 hover:bg-purple-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-purple-500 sm:order-1 sm:ml-3"
						>Create</button
					>
				</div>
			</div>
			<!-- Pinned projects -->
			<div class="px-4 mt-6 sm:px-6 lg:px-8">
				<!-- This example requires Tailwind CSS v2.0+ -->
				<div class="lg:flex lg:h-full lg:flex-col">
					<header
						class="relative z-20 flex items-center justify-between border-b border-gray-200 py-4 px-6 lg:flex-none"
					>
						<h1 class="text-lg font-semibold text-gray-900">
							<time datetime="2022-01">January 2022</time>
						</h1>
						<div class="flex items-center">
							<div class="flex items-center rounded-md shadow-sm md:items-stretch">
								<button
									type="button"
									class="flex items-center justify-center rounded-l-md border border-r-0 border-gray-300 bg-white py-2 pl-3 pr-4 text-gray-400 hover:text-gray-500 focus:relative md:w-9 md:px-2 md:hover:bg-gray-50"
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
									class="hidden border-t border-b border-gray-300 bg-white px-3.5 text-sm font-medium text-gray-700 hover:bg-gray-50 hover:text-gray-900 focus:relative md:block"
									>Today</button
								>
								<span class="relative -mx-px h-5 w-px bg-gray-300 md:hidden" />
								<button
									type="button"
									class="flex items-center justify-center rounded-r-md border border-l-0 border-gray-300 bg-white py-2 pl-4 pr-3 text-gray-400 hover:text-gray-500 focus:relative md:w-9 md:px-2 md:hover:bg-gray-50"
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
							<div class="hidden md:ml-4 md:flex md:items-center">
								<div class="relative">
									<button
										type="button"
										class="flex items-center rounded-md border border-gray-300 bg-white py-2 pl-3 pr-2 text-sm font-medium text-gray-700 shadow-sm hover:bg-gray-50"
										id="menu-button"
										aria-expanded="false"
										aria-haspopup="true"
									>
										Month view
										<!-- Heroicon name: solid/chevron-down -->
										<svg
											class="ml-2 h-5 w-5 text-gray-400"
											xmlns="http://www.w3.org/2000/svg"
											viewBox="0 0 20 20"
											fill="currentColor"
											aria-hidden="true"
										>
											<path
												fill-rule="evenodd"
												d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z"
												clip-rule="evenodd"
											/>
										</svg>
									</button>

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
										class="focus:outline-none absolute right-0 mt-3 w-36 origin-top-right overflow-hidden rounded-md bg-white shadow-lg ring-1 ring-black ring-opacity-5"
										role="menu"
										aria-orientation="vertical"
										aria-labelledby="menu-button"
										tabindex="-1"
									>
										<div class="py-1" role="none">
											<!-- Active: "bg-gray-100 text-gray-900", Not Active: "text-gray-700" -->
											<a
												href="#"
												class="text-gray-700 block px-4 py-2 text-sm"
												role="menuitem"
												tabindex="-1"
												id="menu-item-0">Day view</a
											>
											<a
												href="#"
												class="text-gray-700 block px-4 py-2 text-sm"
												role="menuitem"
												tabindex="-1"
												id="menu-item-1">Week view</a
											>
											<a
												href="#"
												class="text-gray-700 block px-4 py-2 text-sm"
												role="menuitem"
												tabindex="-1"
												id="menu-item-2">Month view</a
											>
											<a
												href="#"
												class="text-gray-700 block px-4 py-2 text-sm"
												role="menuitem"
												tabindex="-1"
												id="menu-item-3">Year view</a
											>
										</div>
									</div>
								</div>
								<div class="ml-6 h-6 w-px bg-gray-300" />
								<button
									type="button"
									class="focus:outline-none ml-6 rounded-md border border-transparent bg-indigo-600 py-2 px-4 text-sm font-medium text-white shadow-sm hover:bg-indigo-700 focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2"
									>Add event</button
								>
							</div>
							<div class="relative ml-6 md:hidden">
								<button
									type="button"
									class="-mx-2 flex items-center rounded-full border border-transparent p-2 text-gray-400 hover:text-gray-500"
									id="menu-0-button"
									aria-expanded="false"
									aria-haspopup="true"
								>
									<span class="sr-only">Open menu</span>
									<!-- Heroicon name: solid/dots-horizontal -->
									<svg
										class="h-5 w-5"
										xmlns="http://www.w3.org/2000/svg"
										viewBox="0 0 20 20"
										fill="currentColor"
										aria-hidden="true"
									>
										<path
											d="M6 10a2 2 0 11-4 0 2 2 0 014 0zM12 10a2 2 0 11-4 0 2 2 0 014 0zM16 12a2 2 0 100-4 2 2 0 000 4z"
										/>
									</svg>
								</button>

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
									class="focus:outline-none absolute right-0 mt-3 w-36 origin-top-right divide-y divide-gray-100 overflow-hidden rounded-md bg-white shadow-lg ring-1 ring-black ring-opacity-5"
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
											id="menu-0-item-0">Create event</a
										>
									</div>
									<div class="py-1" role="none">
										<a
											href="#"
											class="text-gray-700 block px-4 py-2 text-sm"
											role="menuitem"
											tabindex="-1"
											id="menu-0-item-1">Go to today</a
										>
									</div>
									<div class="py-1" role="none">
										<a
											href="#"
											class="text-gray-700 block px-4 py-2 text-sm"
											role="menuitem"
											tabindex="-1"
											id="menu-0-item-2">Day view</a
										>
										<a
											href="#"
											class="text-gray-700 block px-4 py-2 text-sm"
											role="menuitem"
											tabindex="-1"
											id="menu-0-item-3">Week view</a
										>
										<a
											href="#"
											class="text-gray-700 block px-4 py-2 text-sm"
											role="menuitem"
											tabindex="-1"
											id="menu-0-item-4">Month view</a
										>
										<a
											href="#"
											class="text-gray-700 block px-4 py-2 text-sm"
											role="menuitem"
											tabindex="-1"
											id="menu-0-item-5">Year view</a
										>
									</div>
								</div>
							</div>
						</div>
					</header>
					<div class="shadow ring-1 ring-black ring-opacity-5 lg:flex lg:flex-auto lg:flex-col">
						<div
							class="grid grid-cols-7 gap-px border-b border-gray-300 bg-gray-200 text-center text-xs font-semibold leading-6 text-gray-700 lg:flex-none"
						>
							<div class="bg-white py-2">M<span class="sr-only sm:not-sr-only">on</span></div>
							<div class="bg-white py-2">T<span class="sr-only sm:not-sr-only">ue</span></div>
							<div class="bg-white py-2">W<span class="sr-only sm:not-sr-only">ed</span></div>
							<div class="bg-white py-2">T<span class="sr-only sm:not-sr-only">hu</span></div>
							<div class="bg-white py-2">F<span class="sr-only sm:not-sr-only">ri</span></div>
							<div class="bg-white py-2">S<span class="sr-only sm:not-sr-only">at</span></div>
							<div class="bg-white py-2">S<span class="sr-only sm:not-sr-only">un</span></div>
						</div>
						<div class="flex bg-gray-200 text-xs leading-6 text-gray-700 lg:flex-auto">
							<div class="hidden w-full lg:grid lg:grid-cols-7 lg:grid-rows-6 lg:gap-px">
								<!--
            Always include: "relative py-2 px-3"
            Is current month, include: "bg-white"
            Is not current month, include: "bg-gray-50 text-gray-500"
          -->
								<div class="relative bg-gray-50 py-2 px-3 text-gray-500">
									<!--
              Is today, include: "flex h-6 w-6 items-center justify-center rounded-full bg-indigo-600 font-semibold text-white"
            -->
									<time datetime="2021-12-27">27</time>
								</div>
								<div class="relative bg-gray-50 py-2 px-3 text-gray-500">
									<time datetime="2021-12-28">28</time>
								</div>
								<div class="relative bg-gray-50 py-2 px-3 text-gray-500">
									<time datetime="2021-12-29">29</time>
								</div>
								<div class="relative bg-gray-50 py-2 px-3 text-gray-500">
									<time datetime="2021-12-30">30</time>
								</div>
								<div class="relative bg-gray-50 py-2 px-3 text-gray-500">
									<time datetime="2021-12-31">31</time>
								</div>
								<div class="relative bg-white py-2 px-3">
									<time datetime="2022-01-01">1</time>
								</div>
								<div class="relative bg-white py-2 px-3">
									<time datetime="2022-01-01">2</time>
								</div>
								<div class="relative bg-white py-2 px-3">
									<time datetime="2022-01-03">3</time>
									<ol class="mt-2">
										<li>
											<a href="#" class="group flex">
												<p
													class="flex-auto truncate font-medium text-gray-900 group-hover:text-indigo-600"
												>
													Design review
												</p>
												<time
													datetime="2022-01-03T10:00"
													class="ml-3 hidden flex-none text-gray-500 group-hover:text-indigo-600 xl:block"
													>10AM</time
												>
											</a>
										</li>
										<li>
											<a href="#" class="group flex">
												<p
													class="flex-auto truncate font-medium text-gray-900 group-hover:text-indigo-600"
												>
													Sales meeting
												</p>
												<time
													datetime="2022-01-03T14:00"
													class="ml-3 hidden flex-none text-gray-500 group-hover:text-indigo-600 xl:block"
													>2PM</time
												>
											</a>
										</li>
									</ol>
								</div>
								<div class="relative bg-white py-2 px-3">
									<time datetime="2022-01-04">4</time>
								</div>
								<div class="relative bg-white py-2 px-3">
									<time datetime="2022-01-05">5</time>
								</div>
								<div class="relative bg-white py-2 px-3">
									<time datetime="2022-01-06">6</time>
								</div>
								<div class="relative bg-white py-2 px-3">
									<time datetime="2022-01-07">7</time>
									<ol class="mt-2">
										<li>
											<a href="#" class="group flex">
												<p
													class="flex-auto truncate font-medium text-gray-900 group-hover:text-indigo-600"
												>
													Date night
												</p>
												<time
													datetime="2022-01-08T18:00"
													class="ml-3 hidden flex-none text-gray-500 group-hover:text-indigo-600 xl:block"
													>6PM</time
												>
											</a>
										</li>
									</ol>
								</div>
								<div class="relative bg-white py-2 px-3">
									<time datetime="2022-01-08">8</time>
								</div>
								<div class="relative bg-white py-2 px-3">
									<time datetime="2022-01-09">9</time>
								</div>
								<div class="relative bg-white py-2 px-3">
									<time datetime="2022-01-10">10</time>
								</div>
								<div class="relative bg-white py-2 px-3">
									<time datetime="2022-01-11">11</time>
								</div>
								<div class="relative bg-white py-2 px-3">
									<time
										datetime="2022-01-12"
										class="flex h-6 w-6 items-center justify-center rounded-full bg-indigo-600 font-semibold text-white"
										>12</time
									>
									<ol class="mt-2">
										<li>
											<a href="#" class="group flex">
												<p
													class="flex-auto truncate font-medium text-gray-900 group-hover:text-indigo-600"
												>
													Sam's birthday party
												</p>
												<time
													datetime="2022-01-25T14:00"
													class="ml-3 hidden flex-none text-gray-500 group-hover:text-indigo-600 xl:block"
													>2PM</time
												>
											</a>
										</li>
									</ol>
								</div>
								<div class="relative bg-white py-2 px-3">
									<time datetime="2022-01-13">13</time>
								</div>
								<div class="relative bg-white py-2 px-3">
									<time datetime="2022-01-14">14</time>
								</div>
								<div class="relative bg-white py-2 px-3">
									<time datetime="2022-01-15">15</time>
								</div>
								<div class="relative bg-white py-2 px-3">
									<time datetime="2022-01-16">16</time>
								</div>
								<div class="relative bg-white py-2 px-3">
									<time datetime="2022-01-17">17</time>
								</div>
								<div class="relative bg-white py-2 px-3">
									<time datetime="2022-01-18">18</time>
								</div>
								<div class="relative bg-white py-2 px-3">
									<time datetime="2022-01-19">19</time>
								</div>
								<div class="relative bg-white py-2 px-3">
									<time datetime="2022-01-20">20</time>
								</div>
								<div class="relative bg-white py-2 px-3">
									<time datetime="2022-01-21">21</time>
								</div>
								<div class="relative bg-white py-2 px-3">
									<time datetime="2022-01-22">22</time>
									<ol class="mt-2">
										<li>
											<a href="#" class="group flex">
												<p
													class="flex-auto truncate font-medium text-gray-900 group-hover:text-indigo-600"
												>
													Maple syrup museum
												</p>
												<time
													datetime="2022-01-22T15:00"
													class="ml-3 hidden flex-none text-gray-500 group-hover:text-indigo-600 xl:block"
													>3PM</time
												>
											</a>
										</li>
										<li>
											<a href="#" class="group flex">
												<p
													class="flex-auto truncate font-medium text-gray-900 group-hover:text-indigo-600"
												>
													Hockey game
												</p>
												<time
													datetime="2022-01-22T19:00"
													class="ml-3 hidden flex-none text-gray-500 group-hover:text-indigo-600 xl:block"
													>7PM</time
												>
											</a>
										</li>
									</ol>
								</div>
								<div class="relative bg-white py-2 px-3">
									<time datetime="2022-01-23">23</time>
								</div>
								<div class="relative bg-white py-2 px-3">
									<time datetime="2022-01-24">24</time>
								</div>
								<div class="relative bg-white py-2 px-3">
									<time datetime="2022-01-25">25</time>
								</div>
								<div class="relative bg-white py-2 px-3">
									<time datetime="2022-01-26">26</time>
								</div>
								<div class="relative bg-white py-2 px-3">
									<time datetime="2022-01-27">27</time>
								</div>
								<div class="relative bg-white py-2 px-3">
									<time datetime="2022-01-28">28</time>
								</div>
								<div class="relative bg-white py-2 px-3">
									<time datetime="2022-01-29">29</time>
								</div>
								<div class="relative bg-white py-2 px-3">
									<time datetime="2022-01-30">30</time>
								</div>
								<div class="relative bg-white py-2 px-3">
									<time datetime="2022-01-31">31</time>
								</div>
								<div class="relative bg-gray-50 py-2 px-3 text-gray-500">
									<time datetime="2022-02-01">1</time>
								</div>
								<div class="relative bg-gray-50 py-2 px-3 text-gray-500">
									<time datetime="2022-02-02">2</time>
								</div>
								<div class="relative bg-gray-50 py-2 px-3 text-gray-500">
									<time datetime="2022-02-03">3</time>
								</div>
								<div class="relative bg-gray-50 py-2 px-3 text-gray-500">
									<time datetime="2022-02-04">4</time>
									<ol class="mt-2">
										<li>
											<a href="#" class="group flex">
												<p
													class="flex-auto truncate font-medium text-gray-900 group-hover:text-indigo-600"
												>
													Cinema with friends
												</p>
												<time
													datetime="2022-02-04T21:00"
													class="ml-3 hidden flex-none text-gray-500 group-hover:text-indigo-600 xl:block"
													>9PM</time
												>
											</a>
										</li>
									</ol>
								</div>
								<div class="relative bg-gray-50 py-2 px-3 text-gray-500">
									<time datetime="2022-02-05">5</time>
								</div>
								<div class="relative bg-gray-50 py-2 px-3 text-gray-500">
									<time datetime="2022-02-06">6</time>
								</div>
							</div>
							<div class="isolate grid w-full grid-cols-7 grid-rows-6 gap-px lg:hidden">
								<!--
            Always include: "flex h-14 flex-col py-2 px-3 hover:bg-gray-100 focus:z-10"
            Is current month, include: "bg-white"
            Is not current month, include: "bg-gray-50"
            Is selected or is today, include: "font-semibold"
            Is selected, include: "text-white"
            Is not selected and is today, include: "text-indigo-600"
            Is not selected and is current month, and is not today, include: "text-gray-900"
            Is not selected, is not current month, and is not today: "text-gray-500"
          -->
								<button
									type="button"
									class="flex h-14 flex-col bg-gray-50 py-2 px-3 text-gray-500 hover:bg-gray-100 focus:z-10"
								>
									<!--
              Always include: "ml-auto"
              Is selected, include: "flex h-6 w-6 items-center justify-center rounded-full"
              Is selected and is today, include: "bg-indigo-600"
              Is selected and is not today, include: "bg-gray-900"
            -->
									<time datetime="2021-12-27" class="ml-auto">27</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-gray-50 py-2 px-3 text-gray-500 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2021-12-28" class="ml-auto">28</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-gray-50 py-2 px-3 text-gray-500 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2021-12-29" class="ml-auto">29</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-gray-50 py-2 px-3 text-gray-500 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2021-12-30" class="ml-auto">30</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-gray-50 py-2 px-3 text-gray-500 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2021-12-31" class="ml-auto">31</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-white py-2 px-3 text-gray-900 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-01-01" class="ml-auto">1</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-white py-2 px-3 text-gray-900 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-01-02" class="ml-auto">2</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-white py-2 px-3 text-gray-900 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-01-03" class="ml-auto">3</time>
									<p class="sr-only">2 events</p>
									<div class="-mx-0.5 mt-auto flex flex-wrap-reverse">
										<div class="mx-0.5 mb-1 h-1.5 w-1.5 rounded-full bg-gray-400" />
										<div class="mx-0.5 mb-1 h-1.5 w-1.5 rounded-full bg-gray-400" />
									</div>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-white py-2 px-3 text-gray-900 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-01-04" class="ml-auto">4</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-white py-2 px-3 text-gray-900 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-01-05" class="ml-auto">5</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-white py-2 px-3 text-gray-900 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-01-06" class="ml-auto">6</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-white py-2 px-3 text-gray-900 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-01-07" class="ml-auto">7</time>
									<p class="sr-only">1 event</p>
									<div class="-mx-0.5 mt-auto flex flex-wrap-reverse">
										<div class="mx-0.5 mb-1 h-1.5 w-1.5 rounded-full bg-gray-400" />
									</div>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-white py-2 px-3 text-gray-900 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-01-08" class="ml-auto">8</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-white py-2 px-3 text-gray-900 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-01-09" class="ml-auto">9</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-white py-2 px-3 text-gray-900 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-01-10" class="ml-auto">10</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-white py-2 px-3 text-gray-900 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-01-11" class="ml-auto">11</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-white py-2 px-3 font-semibold text-indigo-600 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-01-12" class="ml-auto">12</time>
									<p class="sr-only">1 event</p>
									<div class="-mx-0.5 mt-auto flex flex-wrap-reverse">
										<div class="mx-0.5 mb-1 h-1.5 w-1.5 rounded-full bg-gray-400" />
									</div>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-white py-2 px-3 text-gray-900 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-01-13" class="ml-auto">13</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-white py-2 px-3 text-gray-900 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-01-14" class="ml-auto">14</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-white py-2 px-3 text-gray-900 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-01-15" class="ml-auto">15</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-white py-2 px-3 text-gray-900 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-01-16" class="ml-auto">16</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-white py-2 px-3 text-gray-900 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-01-17" class="ml-auto">17</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-white py-2 px-3 text-gray-900 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-01-18" class="ml-auto">18</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-white py-2 px-3 text-gray-900 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-01-19" class="ml-auto">19</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-white py-2 px-3 text-gray-900 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-01-20" class="ml-auto">20</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-white py-2 px-3 text-gray-900 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-01-21" class="ml-auto">21</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-white py-2 px-3 font-semibold text-white hover:bg-gray-100 focus:z-10"
								>
									<time
										datetime="2022-01-22"
										class="ml-auto flex h-6 w-6 items-center justify-center rounded-full bg-gray-900"
										>22</time
									>
									<p class="sr-only">2 events</p>
									<div class="-mx-0.5 mt-auto flex flex-wrap-reverse">
										<div class="mx-0.5 mb-1 h-1.5 w-1.5 rounded-full bg-gray-400" />
										<div class="mx-0.5 mb-1 h-1.5 w-1.5 rounded-full bg-gray-400" />
									</div>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-white py-2 px-3 text-gray-900 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-01-23" class="ml-auto">23</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-white py-2 px-3 text-gray-900 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-01-24" class="ml-auto">24</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-white py-2 px-3 text-gray-900 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-01-25" class="ml-auto">25</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-white py-2 px-3 text-gray-900 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-01-26" class="ml-auto">26</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-white py-2 px-3 text-gray-900 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-01-27" class="ml-auto">27</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-white py-2 px-3 text-gray-900 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-01-28" class="ml-auto">28</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-white py-2 px-3 text-gray-900 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-01-29" class="ml-auto">29</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-white py-2 px-3 text-gray-900 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-01-30" class="ml-auto">30</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-white py-2 px-3 text-gray-900 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-01-31" class="ml-auto">31</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-gray-50 py-2 px-3 text-gray-500 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-02-01" class="ml-auto">1</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-gray-50 py-2 px-3 text-gray-500 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-02-02" class="ml-auto">2</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-gray-50 py-2 px-3 text-gray-500 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-02-03" class="ml-auto">3</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-gray-50 py-2 px-3 text-gray-500 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-02-04" class="ml-auto">4</time>
									<p class="sr-only">1 event</p>
									<div class="-mx-0.5 mt-auto flex flex-wrap-reverse">
										<div class="mx-0.5 mb-1 h-1.5 w-1.5 rounded-full bg-gray-400" />
									</div>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-gray-50 py-2 px-3 text-gray-500 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-02-05" class="ml-auto">5</time>
									<p class="sr-only">0 events</p>
								</button>
								<button
									type="button"
									class="flex h-14 flex-col bg-gray-50 py-2 px-3 text-gray-500 hover:bg-gray-100 focus:z-10"
								>
									<time datetime="2022-02-06" class="ml-auto">6</time>
									<p class="sr-only">0 events</p>
								</button>
							</div>
						</div>
					</div>
					<div class="py-10 px-4 sm:px-6 lg:hidden">
						<ol
							class="divide-y divide-gray-100 overflow-hidden rounded-lg bg-white text-sm shadow ring-1 ring-black ring-opacity-5"
						>
							<li class="group flex p-4 pr-6 focus-within:bg-gray-50 hover:bg-gray-50">
								<div class="flex-auto">
									<p class="font-semibold text-gray-900">Maple syrup museum</p>
									<time datetime="2022-01-15T09:00" class="mt-2 flex items-center text-gray-700">
										<!-- Heroicon name: solid/clock -->
										<svg
											class="mr-2 h-5 w-5 text-gray-400"
											xmlns="http://www.w3.org/2000/svg"
											viewBox="0 0 20 20"
											fill="currentColor"
											aria-hidden="true"
										>
											<path
												fill-rule="evenodd"
												d="M10 18a8 8 0 100-16 8 8 0 000 16zm1-12a1 1 0 10-2 0v4a1 1 0 00.293.707l2.828 2.829a1 1 0 101.415-1.415L11 9.586V6z"
												clip-rule="evenodd"
											/>
										</svg>
										3PM
									</time>
								</div>
								<a
									href="#"
									class="ml-6 flex-none self-center rounded-md border border-gray-300 bg-white py-2 px-3 font-semibold text-gray-700 opacity-0 shadow-sm hover:bg-gray-50 focus:opacity-100 group-hover:opacity-100"
									>Edit<span class="sr-only">, Maple syrup museum</span></a
								>
							</li>

							<li class="group flex p-4 pr-6 focus-within:bg-gray-50 hover:bg-gray-50">
								<div class="flex-auto">
									<p class="font-semibold text-gray-900">Hockey game</p>
									<time datetime="2022-01-22T19:00" class="mt-2 flex items-center text-gray-700">
										<!-- Heroicon name: solid/clock -->
										<svg
											class="mr-2 h-5 w-5 text-gray-400"
											xmlns="http://www.w3.org/2000/svg"
											viewBox="0 0 20 20"
											fill="currentColor"
											aria-hidden="true"
										>
											<path
												fill-rule="evenodd"
												d="M10 18a8 8 0 100-16 8 8 0 000 16zm1-12a1 1 0 10-2 0v4a1 1 0 00.293.707l2.828 2.829a1 1 0 101.415-1.415L11 9.586V6z"
												clip-rule="evenodd"
											/>
										</svg>
										7PM
									</time>
								</div>
								<a
									href="#"
									class="ml-6 flex-none self-center rounded-md border border-gray-300 bg-white py-2 px-3 font-semibold text-gray-700 opacity-0 shadow-sm hover:bg-gray-50 focus:opacity-100 group-hover:opacity-100"
									>Edit<span class="sr-only">, Hockey game</span></a
								>
							</li>
						</ol>
					</div>
				</div>
			</div>

			<!-- Projects list (only on smallest breakpoint) -->
			<div class="mt-10 sm:hidden">
				<div class="px-4 sm:px-6">
					<h2 class="text-gray-500 text-xs font-medium uppercase tracking-wide">Projects</h2>
				</div>
				<ul role="list" class="mt-3 border-t border-gray-200 divide-y divide-gray-100">
					<li>
						<a
							href="#"
							class="group flex items-center justify-between px-4 py-4 hover:bg-gray-50 sm:px-6"
						>
							<span class="flex items-center truncate space-x-3">
								<span
									class="w-2.5 h-2.5 flex-shrink-0 rounded-full bg-pink-600"
									aria-hidden="true"
								/>
								<span class="font-medium truncate text-sm leading-6">
									GraphQL API
									<span class="truncate font-normal text-gray-500">in Engineering</span>
								</span>
							</span>
							<!-- Heroicon name: solid/chevron-right -->
							<svg
								class="ml-4 h-5 w-5 text-gray-400 group-hover:text-gray-500"
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
						</a>
					</li>

					<!-- More projects... -->
				</ul>
			</div>

			<!-- Projects table (small breakpoint and up) -->
			<div class="hidden mt-8 sm:block">
				<div class="align-middle inline-block min-w-full border-b border-gray-200">
					<table class="min-w-full">
						<thead>
							<tr class="border-t border-gray-200">
								<th
									class="px-6 py-3 border-b border-gray-200 bg-gray-50 text-left text-xs font-medium text-gray-500 uppercase tracking-wider"
								>
									<span class="lg:pl-2">Project</span>
								</th>
								<th
									class="px-6 py-3 border-b border-gray-200 bg-gray-50 text-left text-xs font-medium text-gray-500 uppercase tracking-wider"
									>Members</th
								>
								<th
									class="hidden md:table-cell px-6 py-3 border-b border-gray-200 bg-gray-50 text-right text-xs font-medium text-gray-500 uppercase tracking-wider"
									>Last updated</th
								>
								<th
									class="pr-6 py-3 border-b border-gray-200 bg-gray-50 text-right text-xs font-medium text-gray-500 uppercase tracking-wider"
								/>
							</tr>
						</thead>
						<tbody class="bg-white divide-y divide-gray-100">
							<tr>
								<td
									class="px-6 py-3 max-w-0 w-full whitespace-nowrap text-sm font-medium text-gray-900"
								>
									<div class="flex items-center space-x-3 lg:pl-2">
										<div
											class="flex-shrink-0 w-2.5 h-2.5 rounded-full bg-pink-600"
											aria-hidden="true"
										/>
										<a href="#" class="truncate hover:text-gray-600">
											<span>
												GraphQL API
												<span class="text-gray-500 font-normal">in Engineering</span>
											</span>
										</a>
									</div>
								</td>
								<td class="px-6 py-3 text-sm text-gray-500 font-medium">
									<div class="flex items-center space-x-2">
										<div class="flex flex-shrink-0 -space-x-1">
											<img
												class="max-w-none h-6 w-6 rounded-full ring-2 ring-white"
												src="https://images.unsplash.com/photo-1506794778202-cad84cf45f1d?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80"
												alt="Dries Vincent"
											/>

											<img
												class="max-w-none h-6 w-6 rounded-full ring-2 ring-white"
												src="https://images.unsplash.com/photo-1517841905240-472988babdf9?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80"
												alt="Lindsay Walton"
											/>

											<img
												class="max-w-none h-6 w-6 rounded-full ring-2 ring-white"
												src="https://images.unsplash.com/photo-1438761681033-6461ffad8d80?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80"
												alt="Courtney Henry"
											/>

											<img
												class="max-w-none h-6 w-6 rounded-full ring-2 ring-white"
												src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80"
												alt="Tom Cook"
											/>
										</div>

										<span class="flex-shrink-0 text-xs leading-5 font-medium">+8</span>
									</div>
								</td>
								<td
									class="hidden md:table-cell px-6 py-3 whitespace-nowrap text-sm text-gray-500 text-right"
									>March 17, 2020</td
								>
								<td class="px-6 py-3 whitespace-nowrap text-right text-sm font-medium">
									<a href="#" class="text-indigo-600 hover:text-indigo-900">Edit</a>
								</td>
							</tr>

							<!-- More projects... -->
						</tbody>
					</table>
				</div>
			</div>
		</main>
	</div>
</div>
