# Less App Coding Dojo

## Project Setup Instructions:

1. Create a new npm project by running the ff. in your terminal:
   ```cmd
   npm init -y
   ```
2. Install `less` by running the ff.:
   ```cmd
   npm install --save-dev less
   ```
3. Create a `.gitignore` file containing the `node_modules` folder.
   ```
   node_modules
   ```
4. Create a `src` folder by running the ff.:
   ```cmd
   mkdir src
   ```
5. Create an empty `index.less` file in `src` folder.
6. Write an npm script for transpiling your `less codes to css` by adding the below property in your `package.json` under `scripts`.
   ```json
   "less:compile": "lessc src/index.less src/index.css"
   ```
7. Run the compile script by running the ff. in your terminal:

   ```cmd
   npm run less:compile
   ```

   After running the command, an empty `index.css` file must be created in your `src` folder.

   _Note: The generated `index.css` file is empty because we still haven't written anything in our `index.less` file yet._

8. Create an `index.html` file under `src` folder and populate it using the codes below:
   ```html
   <!DOCTYPE html>
   <html lang="en">
     <head>
       <meta charset="UTF-8" />
       <meta http-equiv="X-UA-Compatible" content="IE=edge" />
       <meta name="viewport" content="width=device-width, initial-scale=1.0" />
       <title>Less App</title>
     </head>
     <body></body>
   </html>
   ```
9. Insert `index.css` in `index.html` by adding a `link` element inside `head`.

   ```html
   <link rel="stylesheet" href="index.css" />
   ```

10. In your `index.html`, add the ff. elements inside `body`:

    ```html
    <button class="btn btn-sm">Small Button</button>
    <button class="btn btn-sm btn-red">Small Red Button</button>
    <button class="btn btn-green">Green Button</button>
    <button class="btn btn-lg btn-blue">Large Blue Button</button>
    ```

    After adding the buttons, open `index.html` in your browser. You should be able to see **four** plain buttons.

    _Note: We will create the `btn` classes later using `less` to align the design of the buttons with their names._

## Development Instructions:

_Note: If you need to verify your changes after following a step, run the compile script then either check the `index.css` file for css verification or view `index.html` in your browser for visual verification._

1. Add basic designs to the **four** buttons by creating the `btn` class in `index.less` file.
   ```css
   .btn {
     color: black;
     background: <<your white color>>;
     border: solid black 1px;
     border-radius: 2px;
     cursor: pointer;
     font-size: 13px;
     padding: 5px 20px;
   }
   .btn:hover {
     background: <<your white color>> - 50%;
   }
   ```
2. Extract the value you used for `<<your white color>>` to a variable and name it `white`.

   _Note: Search for the solution._

3. Before we create the classes for `btn` sizes, let us first create a list variable to contain the sizes (sm, lg) and name it `button-sizes`.

   _Note: Search for the solution._

4. Create the **two** classes for `btn` sizes dynamically by looping through the `button-sizes` list variable and defining only **one** class inside the loop. The transpiled css output should be:

   ```css
   .btn.btn-sm {
     font-size: 10px;
     padding: 5px 15px;
   }
   .btn.btn-lg {
     font-size: 16px;
     padding: 9px 25px;
   }
   ```

   _Note: Read in `less`' documentation about `List Functions` for the solution._

5. Remove the multiple declaration of `.btn` from the codes in the loop for `button-sizes` by refactoring using parent selector reference. There should be not changes with the transpiled css output.

   _Note: Read in `less`' documentation for the solution._

6. Before we create the classes for `btn` colors, let us first create a ruleset variable to contain the colors (red, green, blue) and name it `button-colors`. The colors in the ruleset should be named `red`, `green`, `blue`, but you can change their values to whichever `RGB` values you like to use.

   _Note: Read in `less`' documentation about `List Functions` for the solution._

7. Create the **three** classes and **three** hover pseudo-classes for `btn` colors dynamically by looping through the `button-colors` ruleset variable and defining only **one** class and **one** hover pseudo-class inside the loop. It should also use parent selector reference same with **#5**. The transpiled css output should be:

   ```css
   .btn.btn-red {
     color: <<your white color>>;
     background: <<your red color>> !important;
   }
   .btn.btn-red:hover {
     background: <<your red color - 50%>> !important;
   }
   .btn.btn-green {
     color: <<your white color>>;
     background: <<your green color>> !important;
   }
   .btn.btn-green:hover {
     background: <<your green color - 50%>> !important;
   }
   .btn.btn-blue {
     color: <<your white color>>;
     background: <<your blue color>> !important;
   }
   .btn.btn-blue:hover {
     background: <<your blue color - 50%>> !important;
   }
   ```
