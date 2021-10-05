# Angular

- TypeScript is a primary language for Angular application development.
- The default Angular port is 4200 -> in an Internet browser: http://localhost:4200

## Setting the Angular Environment 

~~~shell
sudo npm install -g @angular/cli # g == global
ng version # angular version
~~~

## Create first project

~~~shell
cd myFirstProj
ng new course-manager
# (no to angular routing)
~~~

## Application Files

- package.json 
- angular.json - global application information
- main.ts - the first code which gets executed 
- src -> app -> app.modules.ts - modules are context limiter 
- src -> app -> app.component.ts - @Component is a decorator
  - selector - directive to create html tag 

## Application Directories 

- node_modules - application dependencies 
- src - core of development 

## Init first project

~~~shell
ng serve # compile
# in an Internet browser type: http://localhost:4200

# delete the content of src -> app -> app.component.html

# create a component in src -> app -> app.component.ts
  # see in #### Ex.: app.component.html

# edit the file of src -> app -> app.component.html

# import modules in src -> app -> app.modules.ts
  # import { FormsModule } from '@angular/forms';
~~~

#### Ex.: app.component.html

~~~html

~~~

# Links
