# Usage

## File Extensions

`.opi`: Orbinuity Program Index

`.opc`: Orbinuity Program Compiled

## Variables

### Explanation

- There are 2 kinds of variables: `Build in` and `Custom`.

- `Build in`: Build in variables for now are: `%R`, `%G` and `%B`.

    - `%R`: This is the red color of the pixel under the current pixel.

    - `%G`: This is the green color of the pixel under the current pixel.

    - `%B`: This is the blue color of the pixel under the current pixel.

- `Custom`: Custom variables have: `set` and `get`.

    - `set`: To set a variable you use `%S> 100`, this will set the variable `%S` to 100.

    - `get`: To get a variable you use `%S` this will get the variable `%S`.

### Example

- A real life example may look like this: 
    ```opi
    %A> 255
    %B> 100
    PX> 0, 0, %R, %A, %B
    ```

- So we can set variable `%A` to 255 and `%B` to 100 with we then use with the `PX>`(See [PX Command](#commands)) just like the build in variable `%R`.

## If component

### Inputs

- `?()` has inputs like this `?(FirstNumber Operator SecondNumber | TrueOutput : FalseOutput)`.

### Explanation

- It works like an if statement, the if statement has a few parts: `FirstNumber`, `Operator`, `SecondNumber`, `TrueOutput` and `FalseOutput`

- `FirstNumber`: This is the first number of the if 
statement.

- `Operator`: The operator can be one of five things: `=`, `>`, `<`, `=>`, `=<`.

    - `=`: if `FirstNumber` is the same as `SecondNumber` return `TrueOutput` if not `FalseOutput`

    - `>`: if `FirstNumber` is more as `SecondNumber` return `TrueOutput` if not `FalseOutput`
    
    - `<`: if `FirstNumber` is less as `SecondNumber` return `TrueOutput` if not `FalseOutput`

    - `=>`: if `FirstNumber` is more or the same as `SecondNumber` return `TrueOutput` if not `FalseOutput`

    - `=<`: if `FirstNumber` is less or the same as `SecondNumber` return `TrueOutput` if not `FalseOutput`

### Example

    - A real life example may look like this: 
        ```opi
        %E> ?(%S = 0 | 100 : 255)
        ```
    - So if the variable `%S`(See [Variables](#variables)) is 0 it will return 100 if not 255.

## Commands

### Explanation

    - A command is constructed like this `CM>`, here CM is the command code.

    - The arguments can be set like this `CM> 100, %E`, here CM is the command code and 100 is the first argument separated by a `, ` and the variable `%E` as the second argument.

### Command Codes

    - There are a few command codes, thees are: `LG>`, `SP` and `%V>`, here `V` is a placeholder for the name of the variable.

    - `LG>`: LG accepts infinite arguments that it will print to the screen, WARNING: LG is meant for debugging only!
    
    - `SP>`: See [SP Command](#sp-command)

    - `%V>`: %V lets you set a variable `V` is a placeholder for the name of the variable %V takes 1 argument witch is what you want to set it to(See [Variables](#variables)).

## SP Command

### Inputs

    - `SP>` has 5 inputs like this `SP> x, y, r, g, b`.

### Explanation

    - It sets the pixel at the given location with the arguments: `X position`, `Y position`, `Red`, `Green` and `Blue`

    - `X position`: This is the X position of the pixel you want to color in.

    - `Y position`: This is the Y position of the pixel you want to color in.

    - `Red`: This is the red color of the pixel you want to color in.

    - `Green`: This is the green color of the pixel you want to color in.

    - `Blue`: This is the blue color of the pixel you want to color in.

### Example

    - A real life example may look like this: 
        ```opi
        SP> 0, 0, 255, %S, 127
        ```
    - So here the pixel at 0x0 id set to Red: 255, Green: variable `%S`, Blue: 127.