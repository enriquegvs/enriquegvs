import pygame
import sys

# Inicializar Pygame
pygame.init()

# Definir dimensiones de la ventana
WIDTH, HEIGHT = 800, 600
WINDOW = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption("Carro de Fórmula 1")

# Colores
BLACK = (0, 0, 0)
RED = (255, 0, 0)
WHITE = (255, 255, 255)

# Clase para el carro
class Formula1Car:
    def __init__(self, x, y):
        self.x = x
        self.y = y
        self.width = 100
        self.height = 50

    def draw(self):
        pygame.draw.rect(WINDOW, RED, (self.x, self.y, self.width, self.height))
        pygame.draw.rect(WINDOW, BLACK, (self.x + 10, self.y - 20, 80, 20))

# Función principal del juego
def main():
    car = Formula1Car(100, 300)

    # Bucle principal
    while True:
        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                pygame.quit()
                sys.exit()

        # Dibujar
        WINDOW.fill(WHITE)
        car.draw()

        # Actualizar la pantalla
        pygame.display.update()

# Ejecutar el juego
if __name__ == "__main__":
    main()
