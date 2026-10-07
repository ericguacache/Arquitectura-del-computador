# Compilador y banderas
CXX      := g++
CXXFLAGS := -std=c++17 -Wall -Wextra

# Nombre del ejecutable
TARGET := simulador

# Fuentes y cabeceras: detecta solos lo que haya en la carpeta
SRCS    := $(wildcard *.cpp)
HEADERS := $(wildcard *.h)
OBJS    := $(SRCS:.cpp=.o)

# Regla por defecto: construir el ejecutable
all: $(TARGET)

# Enlazar todos los .o en el ejecutable
$(TARGET): $(OBJS)
	$(CXX) $(CXXFLAGS) -o $(TARGET) $(OBJS)

# Compilar cada .cpp a su .o (recompila si cambia cualquier .h)
%.o: %.cpp $(HEADERS)
	$(CXX) $(CXXFLAGS) -c $< -o $@

# Construir y ejecutar de un golpe
run: $(TARGET)
	./$(TARGET)

# Borrar generados (.o y ejecutable)
clean:
	rm -f $(OBJS) $(TARGET)

# Estas metas no son archivos
.PHONY: all run clean
