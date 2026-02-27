
news portal
-User Login signup
-dashboard
	-all news
	-Create, UPDATE, DELETE
	-author(user name),
	-comments
	-views
	-category
	

Models
tables

-Register user
	id int
	username String
	email String
	password hash
	roles enum('admin','editor','user')
	created_At
	Updated_At
-news
	id int
	title string
	descriptions String
	views int
	public enum('published','draft')
	author  ref('register_user')
	created_At date
	updated_At date
	feature_image image
	comments Strings
-category
	id int
	category_name
	news = ref
	
api end point
	/api/v1/auth/signup/
	/api/v1/auth/login/
	/api/v1/news/create/
	/api/v1/news/update/<int:id>
	/api/v1/news/delete/<int:id>
	/api/v1/news/all_news/
	/api/v1/news/new_details/<slug:title>
	/api/v1/news/comment/
	/api/v1/category/
