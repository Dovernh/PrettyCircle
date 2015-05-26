http://developer.telerik.com/featured/choose-es6-modules-today/

npm init
	remove description, main, author, license

npm i browser-sync --save-dev

browser-sync start --server --files "*.*"

package.json, make sure there is a src directory under the root where the source goes
"scripts": {
	"serverit": "browser-sync start --files 'src/**/*.html, src/**/*.css,src/**/*.js' --server 'src'"
}

npm i jspm/jspm-cli -g
npm i jspm --save-dev

npm run serverit

jspm init
	baseURL: src
	ES6 traspiler: Babel
	
##JSPM

jspm install text css json

touch /.jshintrc
	{ "esnext": true }
	
src/index.html
	add <script src="/jspm_packages/system.js"></script>
		<script src="config.js"></script>
		<script>
			System.import('./startup');  //do not add .js
		</script>
		
	touch src/startup.js
		add sample js like console.log(System)
		
jspm install kendo-ui bootstrap

src/startup.js
	import 'bootstrap/css/bootstrap.css!';
	
	import 'dropdown/dropdown';
	
	/*System.import('dropdown/dropdown').then {
		dropdown => console.log(dropdown/dropdown.value);
	});*/
	
create directory src/dropdown
	touch dropdownTemplate.html
	touch dropdownData.js add json
