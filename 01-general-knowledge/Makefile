.PHONY: all clean mk_objs

LIB_NAME := test
LIB_NAME2 := test_static

# các biến để dễ nhận biết đường dẫn đến các file
CUR_DIR := .
BIN_DIR := $(CUR_DIR)/bin
INC_DIR := $(CUR_DIR)/inc
SRC_DIR := $(CUR_DIR)/src
OBJ_DIR := $(CUR_DIR)/objs

LIB_DIR := $(CUR_DIR)/libs
LIB_STATIC := $(LIB_DIR)/static
LIB_SHARED := $(LIB_DIR)/shared

# viết như này để khi file main.c cần tìm các file inc dùng option -I để trỏ đến các folder cần tìm (chứa các file .h), Liệt kê vào các biến để 
# sau này khi muốn mở rộng chương trình của mình ra có thể viết nhiều folder có chứa file .h có thể link tới các folder khác cũng chứa các file .h sẽ đỡ rối khi dùng biến, dễ sửa
INC_FLAGS := -I $(INC_DIR) 

						
CC := gcc

mk_objs:
	$(CC) -c $(CUR_DIR)/main.c -o $(OBJ_DIR)/main.o $(INC_FLAGS)
#	create static libary
	$(CC) -c $(SRC_DIR)/hello.c -o $(OBJ_DIR)/hello_static.o $(INC_FLAGS) 
	$(CC) -c $(SRC_DIR)/math.c -o $(OBJ_DIR)/math_static.o $(INC_FLAGS)
#	create shared libary
	$(CC) -c -fPIC $(SRC_DIR)/hello.c -o $(OBJ_DIR)/hello_shared.o $(INC_FLAGS)
	$(CC) -c -fPIC $(SRC_DIR)/math.c -o $(OBJ_DIR)/math_shared.o $(INC_FLAGS)

mk_static:
	ar rcs $(LIB_STATIC)/lib$(LIB_NAME2).a $(OBJ_DIR)/hello_static.o $(OBJ_DIR)/math_static.o

mk_shared:
	$(CC) -shared $(OBJ_DIR)/hello_shared.o $(OBJ_DIR)/math_shared.o -o $(LIB_SHARED)/lib$(LIB_NAME).so

install:
	cp -f $(LIB_SHARED)/lib$(LIB_NAME).so /usr/lib 
	cp -f $(LIB_STATIC)/lib$(LIB_NAME2).a /usr/lib
# option -L, -l là khi mà link 1 chương trình với 1 lib thì cái tiên quyết làm sao lib chúng ta nằm ở đâu để mà link
# -L : là thư mục chứa lib mà ta đang cần
# -l : truyền vào lib name ví dụ là test -> libtest.so (hệ thống sẽ tự động đi tìm tên thư viện này)
all: mk_objs mk_static mk_shared install
	$(CC) $(OBJ_DIR)/main.o -L$(LIB_STATIC) -l$(LIB_NAME2) -o $(BIN_DIR)/statically-linked
	$(CC) $(OBJ_DIR)/main.o -L$(LIB_SHARED) -l$(LIB_NAME) -o $(BIN_DIR)/use-shared-library

clean:
	rm -rf $(OBJ_DIR)/*
	rm -rf $(LIB_SHARED)/lib$(LIB_NAME).so
	rm -rf $(BIN_DIR)/use-shared-library
	rm -rf $(LIB_STATIC)/lib$(LIB_NAME2).a
	rm -rf $(BIN_DIR)/statically-linked