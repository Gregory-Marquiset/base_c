NAME            = Nom_du_project
CC              = cc
FLAG            = -Wall -Wextra -Werror -g3

#################################### Libft #####################################
LIBFT_PATH        = libs/libft/
LIBFT_FILE        = libft.a
LIBFT_LIB         = $(addprefix $(LIBFT_PATH), $(LIBFT_FILE))
################################### Includes ###################################
INC_DIR            = includes/
#################################### Source ####################################
SRC_DIR            = sources/
SRC                = $(addprefix $(SRC_DIR), $(C_FILE))
C_FILE             = merde.c
#################################### Object ####################################
OBJ_PATH           = .obj/
OBJ                = $(SRC:.c=.o)
OBJ_DIR            = $(addprefix $(OBJ_PATH), $(OBJ))

#################################### Rules #####################################
all: lib $(NAME)

$(NAME): $(OBJ_PATH) $(OBJ_DIR) $(DEP_DIR)
    $(CC) $(FLAG) $(OBJ_DIR) $(LIBFT_LIB) -o $(NAME)


$(OBJ_PATH)%.o:%.c
    mkdir -p $(dir $@)
    $(CC) $(FLAG) -c $< -o $@

$(OBJ_PATH):
    mkdir -p $(OBJ_PATH)

lib:
    @make -C $(LIBFT_PATH)

clean:
    make clean -C $(MLX_PATH)
    make clean -C $(LIBFT_PATH)
    rm -fr $(OBJ_PATH)

fclean: clean
    rm -f $(NAME)
    make fclean -C $(LIBFT_PATH)

re: fclean all

.PHONY: all clean fclean re bonus lib

// -p = creer si non existant
// -C = changer de directory