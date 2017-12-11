# FInput

Fortran Input Module

## Usage

```fortran
subroutine example()
 use FInput
 implicit none
 integer :: a
 integer, dimension(:), allocatable :: b
 integer :: cnt
 
 if(.not. read_file("example_input"))
  print *, "Something went wrong."
  stop
 end if

 if(enable_input_logging("parameter.in") &
  print *, "Logging of used input parameter enabled."


 ! Read scalar value from input
 if(.not. get_parameter("int_val_1", a) &
  print *, "Not found."

 ! Read scalar with default value
 if(.not. get_parameter("int_val_2", a, 2) &
  print *, "Not found, but using default: 2"

 ! Read integer array, size is written in cnt
 if(.not. get_parameter("int_array", b, cnt) &
  print *, "Not found."


 if(disable_input_logging() &
  print *, "Logging disabled"

 return
end subroutine example
```
