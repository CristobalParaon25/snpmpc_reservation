<script>
	import profile from '$lib/image/profile.jpg';
	let userDropdown;
	let Sideopen = false;
</script>

<div class="sticky top-0 z-10 flex-shrink-0 flex h-16 bg-white shadow">
	<button
		type="button"
		class="px-4 border-r border-gray-200 text-gray-500 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-indigo-500 md:hidden"
		on:click={() => (Sideopen = !Sideopen)}
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
			<!-- Profile dropdown -->
			<div class="ml-3 relative">
				<div>
					<button
						type="button"
						class="max-w-xs bg-white flex items-center text-sm rounded-full focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
						id="user-menu-button"
						aria-expanded="false"
						aria-haspopup="true"
						on:click={() => (userDropdown = !userDropdown)}
					>
						<span class="sr-only">Open user menu</span>
						<img class="h-8 w-8 rounded-full" src={profile} alt="" />
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
					style:visibility={userDropdown ? 'visible' : 'hidden'}
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
