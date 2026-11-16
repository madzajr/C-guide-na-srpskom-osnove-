# C-guide-na-srpskom-osnove-
Lagani progoram koj uci kako se koriste osnove u C-u

#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define GREEN "\033[32m"
#define CYAN "\033[36m"
#define RESET "\033[0m"

void pause_screen(void) {
    printf("\nPritisni ENTER za nastavak...");
    getchar();
}

void lesson(int n) {
    printf("\n%s========== LEKCIJA %d ==========%s\n",
           CYAN, n, RESET);

    switch (n) {
    case 1:
        printf("PRVI C PROGRAM\n\n");
        printf("C program pocinje funkcijom main().\n");
        printf("printf() prikazuje tekst na ekranu.\n\n");
        printf("Primer:\n\n");
        printf("int main(void) {\n");
        printf("    printf(\"Hello World!\\n\");\n");
        printf("    return 0;\n");
        printf("}\n\n");
        printf("Zadatak: promeni Hello World u svoje ime.\n");
        break;

    case 2:
        printf("PROMENLJIVE\n\n");
        printf("Promenljive cuvaju podatke.\n\n");
        printf("int age = 15;       // ceo broj\n");
        printf("float price = 9.5;  // decimalni broj\n");
        printf("char letter = 'A';  // jedan karakter\n");
        printf("char name[] = \"Ilija\"; // tekst\n\n");
        printf("Zadatak: napravi promenljivu sa svojim godinama.\n");
        break;

    case 3:
        printf("UNOS I ISPIS\n\n");
        printf("printf() ispisuje podatke.\n");
        printf("scanf() cita unos korisnika.\n\n");
        printf("int number;\n");
        printf("printf(\"Unesi broj: \");\n");
        printf("scanf(\"%%d\", &number);\n");
        printf("printf(\"Uneo si: %%d\", number);\n\n");
        printf("%%d = int, %%f = float, %%c = char\n");
        printf("Zadatak: napravi program koji pita za broj.\n");
        break;

    case 4:
        printf("USLOVI: IF / ELSE\n\n");
        printf("Program moze da donosi odluke.\n\n");
        printf("int age = 18;\n\n");
        printf("if (age >= 18) {\n");
        printf("    printf(\"Punoletan\");\n");
        printf("} else {\n");
        printf("    printf(\"Maloletan\");\n");
        printf("}\n\n");
        printf("Zadatak: proveri da li je broj veci od 10.\n");
        break;

    case 5:
        printf("PETLJE: FOR / WHILE\n\n");
        printf("Petlje ponavljaju naredbe.\n\n");
        printf("for (int i = 1; i <= 5; i++) {\n");
        printf("    printf(\"%%d\\n\", i);\n");
        printf("}\n\n");
        printf("Ovo ispisuje brojeve od 1 do 5.\n");
        printf("Zadatak: ispisi brojeve od 1 do 10.\n");
        break;

    case 6:
        printf("FUNKCIJE\n\n");
        printf("Funkcije organizuju kod u manje delove.\n\n");
        printf("int saberi(int a, int b) {\n");
        printf("    return a + b;\n");
        printf("}\n\n");
        printf("int main(void) {\n");
        printf("    printf(\"%%d\", saberi(5, 3));\n");
        printf("    return 0;\n");
        printf("}\n\n");
        printf("Rezultat je 8.\n");
        break;

    case 7:
        printf("NIZOVI I POKAZIVACI\n\n");
        printf("Niz cuva vise vrednosti istog tipa.\n\n");
        printf("int numbers[3] = {10, 20, 30};\n");
        printf("printf(\"%%d\", numbers[0]);\n\n");
        printf("Pokazivac cuva memorijsku adresu.\n\n");
        printf("int x = 10;\n");
        printf("int *p = &x;\n");
        printf("printf(\"%%d\", *p);\n\n");
        printf("Rezultat je 10.\n");
        break;

    default:
        printf("Lekcija ne postoji.\n");
    }
}

void quiz(void) {
    int answer;
    int score = 0;

    printf("\n%s========== C QUIZ ==========%s\n",
           GREEN, RESET);

    printf("\n1. Koja funkcija ispisuje tekst?\n");
    printf("1) scanf   2) printf   3) return\n");
    printf("> ");
    scanf("%d", &answer);
    if (answer == 2) score++;

    printf("\n2. Koji tip cuva ceo broj?\n");
    printf("1) int   2) char   3) float\n");
    printf("> ");
    scanf("%d", &answer);
    if (answer == 1) score++;

    printf("\n3. Koja petlja moze da ponavlja kod?\n");
    printf("1) printf   2) for   3) include\n");
    printf("> ");
    scanf("%d", &answer);
    if (answer == 2) score++;

    printf("\n4. Sta vraca funkcija?\n");
    printf("1) return   2) include   3) scanf\n");
    printf("> ");
    scanf("%d", &answer);
    if (answer == 1) score++;

    printf("\n5. Koji simbol oznacava pokazivac?\n");
    printf("1) #   2) *   3) !\n");
    printf("> ");
    scanf("%d", &answer);
    if (answer == 2) score++;

    printf("\nREZULTAT: %d/5\n", score);

    if (score == 5)
        printf("ODLICNO! C MASTER! \n");
    else if (score >= 3)
        printf("Dobar posao! Nastavi da vezbas.\n");
    else
        printf("Ponovi lekcije i probaj ponovo.\n");

    while (getchar() != '\n');
}

int main(void) {
    int choice;

    do {
        printf("\n");
        printf(GREEN);
        printf("================================\n");
        printf("       C LEARNING TERMINAL\n");
        printf("================================\n");
        printf(RESET);

        printf(" [1] Prvi C program\n");
        printf(" [2] Promenljive\n");
        printf(" [3] Unos i ispis\n");
        printf(" [4] IF / ELSE\n");
        printf(" [5] FOR / WHILE\n");
        printf(" [6] Funkcije\n");
        printf(" [7] Nizovi i pokazivaci\n");
        printf(" [8] TEST ZNANJA\n");
        printf(" [0] Izlaz\n");

        printf("\nIzaberi lekciju: ");

        if (scanf("%d", &choice) != 1) {
            printf("Unesi broj!\n");
            while (getchar() != '\n');
            continue;
        }

        while (getchar() != '\n');

        if (choice >= 1 && choice <= 7) {
            lesson(choice);
            pause_screen();
        }
        else if (choice == 8) {
            quiz();
        }
        else if (choice == 0) {
            printf("\nZatvaranje terminala...\n");
        }
        else {
            printf("\nNepostojeca opcija!\n");
        }

    } while (choice != 0);

    return 0;
}
