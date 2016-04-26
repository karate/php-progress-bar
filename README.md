# ProgressBar
A simple progress bar to keep users informed during long-running php scripts.
```
70/100 [============================>            ] - 70%
```

*Based on a StackOverflow comment: http://stackoverflow.com/a/27147177/5805496*
## Usage
Include ProgressBar.php and create a new progress bar
```php
// Suppose you have an array $items with data you want to import
include 'ProgressBar.php';
$bar = new ProgressBar(count($items));
```
Update progress bar on every iteration
```php
foreach ($items as $item) {
  $bar->update();
  // import/update/delete item
}
```
Change the total number of items
```php
// I just found out there are 10 more items
$total = $bar->get_total_items();
$bar->set_total_items($total + 10)
```
Change the length of the progress bar
```php
$bar->set_bar_length(40);
```
Dynamically change the progress bar position
```php
// Set progress to 70/100
$bar->set_total(100);
$bar->update(70);
```
