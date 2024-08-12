print( "Мифическое наследование")

class Horse:
    """класс описывающий лошадь. Объект этого класса обладает следующими атрибутами:"""
    x_distance = 0 #- пройденный путь.
    _sound = 'Frrr'



    def run(self, dx): # где dx - изменение дистанции, увеличивает x_distance на dx.
        self.x_distance += dx
        return self.x_distance



class Eagle:
    """ класс описывающий орла. Объект этого класса обладает следующими атрибутами"""
    y_distance = 0# - высота полёта
    sound = 'I train, eat, sleep, and repeat' # - звук, который издаёт орёл(отсылка)

    def fly(self, dy):
        self.y_distance += dy
        return self.y_distance


class Pegasus(Horse, Eagle):  # класс описывающий пегаса. Наследуется от Horse и Eagle в том же порядке.

    def __init__(self):
         self.sound = super()._sound
         self.sound = super().sound

    def move(self, dx, dy):
        self.run(dx)
        self.fly(dy)
        return (self.x_distance, self.y_distance)


    def get_pos(self):
        return (self.x_distance, self.y_distance)

    def voice(self):
        print(self.sound)
        return self.sound




#def get_pos2( dx, dy):
#    return (dx, dy)



p1 = Pegasus()

print(p1.get_pos())
p1.move(10, 15)
print(p1.get_pos())
p1.move(-5, 20)
print(p1.get_pos())

p1.voice()

