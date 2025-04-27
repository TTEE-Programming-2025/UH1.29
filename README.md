# UH1.29 - 我的作业仓库
#include 
<stdio.h>
#include <stdlib.h>
#include <conio.h> // Windows下使用getch()

// 預設密碼
#define PASSWORD 2025

// 函數宣告
void showWelcomeScreen();
void showMenu();
void drawTriangle();
void showMultiplicationTable();
int passwordCheck();
int main() {
    int success;
    char choice;

    success = passwordCheck();
    if (!success) {
        printf("\n輸入錯誤3次，程式結束！\n");
        return 0;
    }

    do {
        system("cls");
        showMenu();
        printf("請選擇選項: ");
        choice = getch();

        switch (choice) {
            case 'a': case 'A':
                system("cls");
                drawTriangle();
                break;
            case 'b': case 'B':
                system("cls");
                showMultiplicationTable();
                break;
            case 'c': case 'C': {
                char confirm;
                do {
                    printf("\nContinue? (y/n): ");
                    confirm = getch();
                    if (confirm == 'y' || confirm == 'Y')
                        break;
                    else if (confirm == 'n' || confirm == 'N') {
                        printf("\n程式結束，再見！\n");
                        return 0;
                    } else {
                        printf("\n輸入錯誤，請重新輸入！\n");
                    }
                } while (1);
                break;
            }
            default:
                printf("\n無效選項，請重新輸入！\n");
                break;
        }
    } while (1);

    return 0;
}
// 顯示個人風格畫面
void showWelcomeScreen() {
  void showWelcomeScreen() {
    printf("===================================\n");
    printf("|                                 |\n");
    printf("|      Welcome to H1.29 !         |\n");
    printf("|                                 |\n");
    printf("|        C Language Project       |\n");
    printf("|                                 |\n");
    printf("|         工程不分系               |\n");
    printf("|                                 |\n");
    printf("|        Let's go !!!             |\n");
    printf("|                                 |\n");
    printf("===================================\n");
    printf("\n預設密碼為: %d\n", PASSWORD);
}

    printf("\n預設密碼為: %d\n", PASSWORD);
}

// 密碼檢查函數
int passwordCheck() {
    int pwd;
    int attempts = 0;

    showWelcomeScreen();

    while (attempts < 3) {
        printf("\n請輸入密碼: ");
        scanf("%d", &pwd);

        if (pwd == PASSWORD) {
            printf("\n密碼正確，歡迎！\n");
            return 1;
        } else {
            printf("\n密碼錯誤！\n");
            attempts++;
        }
    }
    return 0;
}
