

<h1>Rutgers Nutritional Information Scraper</h1>

This repository contains a Web Scraping Script which scrapes the website food.rutgers.edu for menus and nutritional information.
It then saves the results into a new file.

Official website reports wonky numbers for certain fields, so only scraping calories, serving size, and ingredients for now.

<h3>Dependencies</h3>
- BeautifulSoup

<h3>Format</h3>
Enable indentation with the `--fancy` flag.

Use the `--dicts` flag to organize for easier random access, like so:
```
{
	'Brower Commons' : {
		'Breakfast' : [
			'CATEGORY' : [
				{
					'name' : 'ITEM NAME',
					'serving' : 'SERVING SIZE',
					'calories' : 100,
					'ingredients' : [
						'INGREDIENT1',
						'INGREDIENT2',
						...
					]
				},
				{
					...
				},
				...
			],
			...
		],
		'Lunch' : {
			...
		},
		'Dinner' : {
			...
		},
		'Knight Room' : {
			...
		}
	},
	'Busch Dining Hall' : {
		...
	},
	'Neilson Dining Hall' : {
		...
	},
	'Livingston Dining Commons' : {
		...
	}
}
```

Use without the `--dicts` flag to organize with arrays like the old food API does.
```
[
	{
		'location_name' : 'LOCATION NAME'
		'meals' : [
			{
				'meal_name' : 'MEAL NAME',
				'genres' : [
					{
						'genre_name' : 'CATEGORY NAME'
						'items' : [
							{
								'name' : 'ITEM NAME',
								'serving' : 'SERVING SIZE',
								'calories' : 100,
								'ingredients' : [
									'INGREDIENT1',
									'INGREDIENT2',
									...
								]
							},
							...
						]
					},
					...
				]
			},
			...
		]
	},
	...
]
```


