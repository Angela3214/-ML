# -ML
Это задачи для отбора
import random


class t:
    def __init__(self, n=3):
        self.n = n
        self.table = [[((i * n + i / n + j) % (n * n) + 1) for j in range(n * n)] for i in range(9)]

    def pokaz(self):
        for j in range(self.n ** 2):
            print(self.table[j])

    def trans(self):
        self.table = map(list, zip(*self.table))

    def swap_rows_1(self):
        a = random.randrange(0, self.n, 1)
        b = random.randrange(0, self.n, 1)
        str1 = a * self.n + b
        c = random.randrange(0, self.n, 1)
        str2 = a * self.n + c
        while str1 == str2:
            str2 = random.randrange(0, self.n, 1)
        self.table[str1], self.table[str2] = self.table[str2], self.table[str1]

    def swap_col_1(self):
        t.trans(self)
        t.swap_rows_small(self)
        t.transposing(self)

    def swap_rows_3(self):
        a = random.randrange(0, self.n, 1)
        b = random.randrange(0, self.n, 1)
        while a == b:
            b = random.randrange(0, self.n, 1)
        for i in range(0, self.n):
            k1 = a * self.n
            k2 = b * self.n
            d, c = k1 + i, k2 + i
            self.table[d], self.table[c] = self.table[c], self.table[d]

    def swap_col_3(self):
        t.trans(self)
        t.swap_rows_3(self)
        t.trans(self)

    def pere(self):
        for i in range(40):
            g = random.randrange(0, 4)
            if g == 0:
                t.trans(self)
            if g == 1:
                t.swap_rows_1(self)
            if g == 2:
                t.swap_col_1(self)
            if g == 3:
                t.swap_rows_3(self)
            if g == 4:
                t.swap_col_3(self)


class g:
    def __init__(self, n=3):
        self.n = n
        self.t = t()
        self.sozd()
        self.sozdnew()

    def sozd(self):
        self.t = []

        for i in range(9):
            k = []
            for j in range(9):
                k.append(0)
            self.t.append(k)
        lst = list(range(0, 81))
        random.shuffle(lst)
        for i in range(self.n):
            self.t[lst[i]][lst[i]] += self.matrix.matrix[lst[i]][lst[i]]

        def pokaz(self):
            for j in range(self.n ** 2):
                print(self.table[j])

        def sozdnew(self):
            self.g = []
            for i in range(9):
                r = list()
                for j in range(9):
                    s = set()
                    for k in range(9):
                        s.add(self.t[k])
                        s.add(self.t[k])
                    for m in range(3):
                        for r in range(3):
                            s.add(self.t[(i // 3) * 3 + m][(j // 3) * 3 + r])
                        r.append(s)
                self.g.append(r)


w = g(15)
