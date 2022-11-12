<script>
	import Sidebar from '$lib/components/Sidebar.svelte';
	import Navbar from '$lib/components/Navbar.svelte';
</script>

<Sidebar />
<div class="md:pl-64 flex flex-col">
	<Navbar />

	<main class="flex-1">
		<div class="py-6">
			<div class="max-w-7xl mx-auto px-4 sm:px-6 md:px-8">
				<!-- Replace with your content -->
				<!-- This example requires Tailwind CSS v2.0+ -->
				<div class="flex flex-col">
					<div class="-my-2 overflow-x-auto sm:-mx-6 lg:-mx-8">
						<div class="py-2 align-middle inline-block min-w-full sm:px-6 lg:px-8">
							<div class="shadow overflow-hidden border-b border-gray-200 sm:rounded-lg">
								<table class="min-w-full divide-y divide-gray-200">
									<thead class="bg-gray-50">
										<tr>
											<th
												scope="col"
												class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider"
												>Name</th
											>
											<th
												scope="col"
												class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider"
												>Orders</th
											>
											<th
												scope="col"
												class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider"
												>Schedule</th
											>
											<th
												scope="col"
												class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider"
												>Address</th
											>
											<th scope="col" class="relative px-6 py-3">
												<span class="sr-only">Edit</span>
											</th>
										</tr>
									</thead>
									<tbody>
										<!-- Odd row -->
										<tr class="bg-white">
											<td class="px-6 py-4 whitespace-nowrap text-sm font-medium text-gray-900"
												>Aljon Lerios</td
											>
											<td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500"
												>Birthday Package</td
											>
											<td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500"
												>November 22 2022</td
											>
											<td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500"
												>Plaridel Baybay City</td
											>
											<td class="px-6 py-4 whitespace-nowrap text-right text-sm font-medium">
												<a href="#" class="text-indigo-600 hover:text-indigo-900">Edit</a>
											</td>
										</tr>

										<!-- Even row -->
										<tr class="bg-gray-50">
											<td class="px-6 py-4 whitespace-nowrap text-sm font-medium text-gray-900"
												>Cristobal Paraon</td
											>
											<td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500"
												>Dining Package</td
											>
											<td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">June 24 2022</td
											>
											<td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500"
												>Plaridel Baybay City</td
											>
											<td class="px-6 py-4 whitespace-nowrap text-right text-sm font-medium">
												<a href="#" class="text-indigo-600 hover:text-indigo-900">Edit</a>
											</td>
										</tr>

										<!-- More people... -->
									</tbody>
								</table>
							</div>
						</div>
					</div>
				</div>

				<!-- /End replace -->
			</div>
		</div>
	</main>
</div>
