# react-webpack-babel
Simple React Webpack Babel Starter Kit

This is a simple [React](https://facebook.github.io/react/), [Webpack](http://webpack.github.io/) and [Babel](https://babeljs.io/) application with nothing else in it.

### What's in it?

Simple src/index.jsx and src/index.css with webpack configuration for development (with hot reloading) and production (with minification).
CSS module loading is also configured, so you can include your css via ```import styles from './path/to.css';```.
Both js(x) and css are hot loaded during development.

### To run

* You'll need to have [git](https://git-scm.com/) and [node](https://nodejs.org/en/) installed in your system.
* Fork and clone the project:

```
> $ git clone THIS_REPO_URL
```

* Then install the dependencies:

```
> $ npm install
```

* Run development server:

```
> $ npm start
```

Open the web browser to `http://localhost:8888/`

* Build production package: 

```
> $ npm run build
```

### Nginx Config

Here is the suggested Nginx config:
```
server {
	# ... root and other options

	gzip on;
	gzip_http_version 1.1;
	gzip_types text/plain text/css text/xml application/javascript image/svg+xml;

	location ~ \.html?$ {
		expires 7d;
		add_header K3A html;
	}

	location ~ \.(svg|ttf|js|css|svgz|eot|otf|woff|jpg|jpeg|gif|png|ico)$ {
		access_log off;
		log_not_found off;
		expires max;
		add_header K3A static;
	}
}
```

### Eslint
There is a .eslint.yaml config for eslint ready with React plugin.
To use it, you need to install additional dependencies though:

```
> npm install --save-dev eslint eslint-plugin-react
```

To do the actual linting, run:

```
> npm run lint
```

### Notes on importing css styles
* css styles having /src/ in their absolute path are considered part of the application and exported as local css modules.
* css styles having /node_modules|global)/ in their absolute path are considered global styles used by many components.

### Contribute
Please contribute to the project if you think this can be done better in anyway even for this README :)
