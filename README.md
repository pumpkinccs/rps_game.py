import random

choices = ["taş", "kağıt", "makas"]

def kazanan(kullanici, bilgisayar):
    if kullanici == bilgisayar:
        return "Berabere!"
    elif (kullanici == "taş" and bilgisayar == "makas") or \
         (kullanici == "kağıt" and bilgisayar == "taş") or \
         (kullanici == "makas" and bilgisayar == "kağıt"):
        return "Kazandın!"
    else:
        return "Kaybettin!"

while True:
    user = input("Taş, Kağıt, Makas (çıkmak için q): ").lower()

    if user == "q":
        break

    if user not in choices:
        print("Geçersiz seçim!")
        continue

    comp = random.choice(choices)

    print("Bilgisayar:", comp)
    print(kazanan(user, comp))
