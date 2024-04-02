# Compiler and compiling flags
CC = gcc
CFLAGS = -Wall -Wextra -Werror -pthread

# Name of your program
NAME = philo

# Source files
SRCS = main.c \
       utils.c \
	   utils2.c \
	   utils3.c \

# Object files
OBJS = $(SRCS:.c=.o)

# Compile and link the program
$(NAME): $(OBJS)
	$(CC) $(CFLAGS) $(OBJS) -o $(NAME)

# Rule for creating object files
%.o: %.c
	$(CC) $(CFLAGS) -c $< -o $@

# Clean objects
clean:
	rm -f $(OBJS)

# Full clean (objects + binary)
fclean: clean
	rm -f $(NAME)

# Re-compile
re: fclean $(NAME)

# Phony targets
.PHONY: clean fclean re
