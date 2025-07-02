<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Teraz menu</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap');
        
        body {
            font-family: 'Poppins', sans-serif;
            background-color: #f5f5f5;
            color: #333;
        }
        
        
        .menu-item {
            transition: all 0.3s ease;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
        }
        
        .menu-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 15px rgba(0, 0, 0, 0.1);
        }
        
        .menu-item-image {
            height: 200px;
            object-fit: cover;
            transition: transform 0.3s ease;
        }
        
        .menu-item:hover .menu-item-image {
            transform: scale(1.05);
        }
        
        .tab-active {
            border-bottom: 3px solid #6F4E37;
            color: #6F4E37;
            font-weight: 500;
        }
    </style>
</head>
<body class="min-h-screen pb-20">
    <div class="container mx-auto px-4 py-12">
        <!-- Header -->
        <div class="text-center mb-12">
            <h1 class="text-4xl md:text-5xl font-bold text-[#6F4E37] mb-4">Teraz <span class="text-amber-800">Menu</span></h1>
            <p class="text-lg text-gray-600 max-w-2xl mx-auto">Handcrafted beverages and freshly prepared food made with premium ingredients</p>
        </div>
        
        <!-- Category Tabs -->
        <div class="flex justify-center mb-12 border-b border-gray-200">
            <div class="flex overflow-x-auto" id="category-tabs">
                <button onclick="filterMenu('all')" class="text-sm font-medium px-6 py-3 tab-active whitespace-nowrap">All Menu</button>
                <button onclick="filterMenu('coffee')" class="text-sm font-medium px-6 py-3 whitespace-nowrap">Coffee & Tea</button>
                <button onclick="filterMenu('food')" class="text-sm font-medium px-6 py-3 whitespace-nowrap">Food</button>
                <button onclick="filterMenu('dessert')" class="text-sm font-medium px-6 py-3 whitespace-nowrap">Desserts</button>
            </div>
        </div>
        
        <!-- Search -->
        <div class="max-w-md mx-auto mb-12">
            <div class="relative">
                <input type="text" id="search-input" placeholder="Search menu items..." class="w-full px-4 py-3 rounded-full border border-gray-300 focus:outline-none focus:ring-2 focus:ring-amber-700">
                <button class="absolute right-3 top-3 text-gray-400">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
                    </svg>
                </button>
            </div>
        </div>
        
        <!-- Menu Items Grid -->
        <div class="grid grid-cols-3 gap-4 sm:gap-6" id="menu-items">

            <!-- Coffee Items -->
            <div class="menu-item bg-white rounded-lg overflow-hidden" data-category="coffee">
                <div class="h-48 overflow-hidden">
                    <img src="jadul1.jpg">
                </div>
                <div class="p-6">
                    <h3 class="text-xl font-semibold mb-2">Kopi jadul</h3>
                    <p class="text-gray-600 mb-4">Rich, bold flavor with caramel notes and a silky crema</p>
                </div>
            </div>
            
            <div class="menu-item bg-white rounded-lg overflow-hidden" data-category="coffee">
                <div class="h-48 overflow-hidden">
                    <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/2933ec65-f230-4a92-b442-a686a6ce31a3.png" alt="Creamy latte with latte art in a clear glass mug on a marble counter" class="w-full h-full object-cover">
                </div>
                <div class="p-6">
                    <h3 class="text-xl font-semibold mb-2">Creamy Latte</h3>
                    <p class="text-gray-600 mb-4">Smooth espresso with steamed milk and delicate foam art</p>
                </div>
            </div>
            
            <div class="menu-item bg-white rounded-lg overflow-hidden" data-category="coffee">
                <div class="h-48 overflow-hidden">
                    <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/f0e64ce7-21be-4b43-bb54-2e516eb9d80d.png" alt="Iced matcha latte in a glass with mint leaves and layered green color" class="w-full h-full object-cover">
                </div>
                <div class="p-6">
                    <h3 class="text-xl font-semibold mb-2">Iced Matcha Latte</h3>
                    <p class="text-gray-600 mb-4">Premium ceremonial matcha whisked with oat milk over ice</p>
                </div>
            </div>
            
            <!-- Food Items -->
            <div class="menu-item bg-white rounded-lg overflow-hidden" data-category="food">
                <div class="h-48 overflow-hidden">
                    <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/de43e3f1-7e1a-470a-a219-1814cb8a8527.png" alt="Avocado toast on artisan bread with cherry tomatoes and microgreens" class="w-full h-full object-cover">
                </div>
                <div class="p-6">
                    <h3 class="text-xl font-semibold mb-2">Avocado Toast</h3>
                    <p class="text-gray-600 mb-4">Sourdough bread with smashed avocado, cherry tomatoes, and sea salt</p>
                </div>
            </div>
            
            <div class="menu-item bg-white rounded-lg overflow-hidden" data-category="food">
                <div class="h-48 overflow-hidden">
                    <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/5cbae01f-021f-4517-ba65-45e71d031a70.png" alt="Breakfast sandwich with egg, bacon, and cheese on an english muffin" class="w-full h-full object-cover">
                </div>
                <div class="p-6">
                    <h3 class="text-xl font-semibold mb-2">Morning Sandwich</h3>
                    <p class="text-gray-600 mb-4">English muffin with egg, bacon, cheddar, and garlic aioli</p>
                </div>
            </div>
            
            <!-- Dessert Items -->
            <div class="menu-item bg-white rounded-lg overflow-hidden" data-category="dessert">
                <div class="h-48 overflow-hidden">
                    <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/9a4c1e24-3d02-4c35-a2ac-f102b31ab330.png" alt="Cross section of chocolate croissant showing flaky layers with melted chocolate" class="w-full h-full object-cover">
                </div>
                <div class="p-6">
                    <h3 class="text-xl font-semibold mb-2">Chocolate Croissant</h3>
                    <p class="text-gray-600 mb-4">Buttery, flaky pastry with rich dark chocolate filling</p>
                </div>
            </div>
            
            <div class="menu-item bg-white rounded-lg overflow-hidden" data-category="dessert">
                <div class="h-48 overflow-hidden">
                    <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/d85d2b6f-03c0-4d64-9be2-bd6e1514e2ac.png" alt="Moist banana bread slice with walnuts and cinnamon butter on a wooden board" class="w-full h-full object-cover">
                </div>
                <div class="p-6">
                    <h3 class="text-xl font-semibold mb-2">Banana Walnut Bread</h3>
                    <p class="text-gray-600 mb-4">Homemade bread with ripe bananas, walnuts, and cinnamon</p>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Filter menu items by category
        function filterMenu(category) {
            const items = document.querySelectorAll('.menu-item');
            const tabs = document.querySelectorAll('#category-tabs button');
            
            // Update active tab
            tabs.forEach(tab => {
                tab.classList.remove('tab-active');
                if (tab.textContent.toLowerCase().includes(category) || 
                    (category === 'all' && tab.textContent.toLowerCase().includes('all'))) {
                    tab.classList.add('tab-active');
                }
            });
            
            // Show/hide items based on category
            items.forEach(item => {
                if (category === 'all') {
                    item.style.display = 'block';
                } else {
                    if (item.dataset.category === category) {
                        item.style.display = 'block';
                    } else {
                        item.style.display = 'none';
                    }
                }
            });
        }
        
        // Simple search functionality
        document.getElementById('search-input').addEventListener('input', function(e) {
            const searchTerm = e.target.value.toLowerCase();
            const items = document.querySelectorAll('.menu-item');
            
            items.forEach(item => {
                const title = item.querySelector('h3').textContent.toLowerCase();
                const description = item.querySelector('p').textContent.toLowerCase();
                
                if (title.includes(searchTerm) || description.includes(searchTerm)) {
                    item.style.display = 'block';
                } else {
                    item.style.display = 'none';
                }
            });
        });
       
    </script>
</body>
</html>
