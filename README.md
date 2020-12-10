Grep with Marketing
===================

Sometimes the reason you don't write unit tests is because it's really difficult to isolate a testable unit. 
You can use this code to practice some relevant techniques for that situation.

The overall idea is you'd like to test the `grep` function defined in `main.c`. 
Instructions for one way to do this that demonstrates some useful techniques:

1. Isolate the unit under test by moving it into the 'surgery'. The original code should still compile between each step.
    - [ ] Make sure you can compile and run both main.c in the main project and main.cpp in the surgery, and know how to switch between them.
    - [ ] Copy the 'grep' function into the surgery. Hint - create a new c and h file, copy the code into the c file.
    - [ ] Replace the original function with a #include of the relevant file in the surgery
    - [ ] Run the original compilation - it should still be successful
    
2. Get the 'grep' function to compile in its new home. Note you are done with this when you get linker errors. 
    - [ ] Modify the unit test in the surgery to call the 'grep' function
    - [ ] In the c file, add a #include for the h file, hidden using an #ifdef SURGERY
    - [ ] Double check the original code compiles and runs exactly as before.
    - [ ] Add relevant standard library includes in the h file in the surgery.
    - [ ] Add function prototypes in `stubs.h` for any other functions that the unit under test uses.
    - [ ] Double check the original code compiles and runs exactly as before.  

2. Make the code in the surgery also link by generating [exploding fakes](https://github.com/jwgrenning/gen-xfakes)
    - [ ] Copy your linker error messages into a file, for example `linker-errors.txt`
    - [ ] Use the gen-xfakes.sh script to generate exploding fakes.
    - [ ] Put the exploding fakes in the `x-stubs-cpp.cpp` file so they will be included in the build.
    - [ ] Compile and link the code in the surgery, it should succeed.
   
3. Write a first unit test.
    - [ ] Write a unit test in the surgery that calls the 'grep' function. Run it and find the first explosion.
    - [ ] Replace exploding stubs with real stubs one by one
   
4. Write more unit tests
5. Refactor the unit to be more testable
6. Re-insert the unit into the main code and integrate the tests so they are run as part of the normal build.
