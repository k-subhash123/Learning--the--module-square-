PROJ_NAME= square
SRC=square.c

ifdef os
     RM = del /q
	 FixPath = $(subset /,\,$1)
	 EXEC = exe
else
    ifeq ($(shell uname), Linux)
	    RM = rm -rf
		FixPath = $1
		EXEC = out
	endif
endif

Build:
	gcc $(SRC) -o $(call FixPath,$(PROJ_NAME).$(EXEC)) -lm
run:
	./$(call FixPath,$(PROJ_NAME).$(EXEC))


staticcheck:
	cppcheck --enable=all -iunity .
dynamiccheck:Build
	valgrind ./$(call FixPath,$(PROJ_NAME).$(EXEC))