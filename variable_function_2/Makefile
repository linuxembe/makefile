CC := gcc
MKDIR := mkdir
RM := rm -fr

DIR_OBJS :=objs
DIR_TARGET := target

DIRS := $(DIR_OBJS) $(DIR_TARGET)

TARGET := $(DIR_TARGET)/hello-makefile.out

SRCS := $(wildcard *.c)
OBJS := $(SRCS:.c=.o)
OBJS := $(addprefix $(DIR_OBJS)/, $(OBJS))

.PHONY : rebuild clean all

$(TARGET) : $(DIRS) $(OBJS)
	$(CC) -o $@ $(OBJS)
	@echo "target file ==>$@"
$(DIRS) :
	$(MKDIR) $@

$(DIR_OBJS)/%.o : %.c
	$(CC) -o $@ -c $^

rebuild : clean all

all : $(TARGET)
clean:
	$(RM) $(DIRS)


