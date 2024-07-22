#условные-выражения

Старайтесь писать нормальный вариант выполнения в if, а не else.
Например:
```js
// === Bad ❌
if (response.error) {
	console.log(response.error);
	return null;
} else {
	self.posts = request.data.posts;
	self.posts.sort();
	self.showCategories();
	
	return self.posts.length;
}

// === Good ✅
if (response.ok) {
	self.posts = request.data.posts;
	self.posts.sort();
	self.showCategories();
	
	return self.posts.length;
} else {
	console.log(response.error);
	return null;
}
```