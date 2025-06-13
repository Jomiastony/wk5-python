# wk5-python

class Superhero:
    def __init__(self, name, power, health):
        self.name = name
        self.power = power
        self._health = health 

    def use_power(self):
        print(f"{self.name} uses {self.power}!")

    def take_damage(self, damage):
        self._health -= damage
        status = "has fallen!" if self._health <= 0 else f"has {self._health} health remaining."
        print(f"{self.name} {status}")

class FlyingSuperhero(Superhero):
    def use_power(self):
        super().use_power()
        print(f"{self.name} takes to the sky!")

hero1 = Superhero("IronKnight", "Laser Beam", 1000)
hero2 = FlyingSuperhero("SkyFalcon", "Aerial Strike", 1234)

for hero in [hero1, hero2]:
    hero.use_power()
    hero.take_damage(762)
