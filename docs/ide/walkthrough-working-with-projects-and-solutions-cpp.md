---
title: 'Пошаговое руководство: Работа с проектами и решениями (C++) | Документы Microsoft'
ms.custom: ''
ms.date: 12/13/2017
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- solutions [C++]
- projects [C++], about projects
- projects [C++]
- solutions [C++], about solutions
ms.assetid: 93a3f290-e294-46e3-876e-e3084d9ae833
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f62b2317669949473c8b0e68ad4410a3d9b03806
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-working-with-projects-and-solutions-c"></a>Пошаговое руководство. Работа с проектами и решениями (C++)

В этой статье описано, как создать проект C++ в Visual Studio, добавить код, а затем выполнить сборку и запуск проекта. Проект в этом пошаговом руководстве представляет собой программу, которая отслеживает количество игроков в различных карточных играх.

В Visual Studio организации работы служат проекты и решения. Решение может содержать несколько проектов, например библиотеку DLL и ссылающийся на нее исполняемый файл. Дополнительные сведения см. в статье [Solutions and Projects](/visualstudio/ide/solutions-and-projects-in-visual-studio) (Решения и проекты).

## <a name="before-you-start"></a>Перед началом работы

Для выполнения данного пошагового руководства, вам потребуется Visual Studio 2017 г. версия 15,3 или более поздней версии. При необходимости копии это краткое руководство: [поддержки Установка C++ в Visual Studio](../build/vscpp-step-0-installation.md). Если ее там еще, выполните следующие шаги после установки можно с помощью учебника «Hello, World», чтобы убедиться в правильности установки Visual C++ и он работает.

Это полезно, если владеть основами языка C++ и знать компилятора, компоновщика и отладчика назначение. В учебнике также предполагается, что вы знакомы с Windows и способ использования меню, диалоговых окон,

## <a name="create-a-project"></a>Создание проекта

Чтобы создать проект, сначала выберите шаблон типа проекта. Для каждого типа проекта Visual Studio задает параметры компилятора и — в зависимости от типа — создает стартовый код, который позже можно изменить.

### <a name="to-create-a-project"></a>Создание проекта

1. В строке меню выберите **файл > Создать > проект**.

1. В левой области **новый проект** диалогового окна разверните **установленные** и выберите **Visual C++**, если она еще не является открытым.

1. В списке установленных шаблонов в центральной области выберите **консольного приложения Windows**.

1. Введите имя проекта в **имя** поле. Например, введите **игры**.

   Вы можете принять расположение по умолчанию в **расположение** раскрывающегося списка, ввести другое расположение или нажать **Обзор** кнопку, чтобы перейти к каталогу, где требуется сохранить проект.

   При создании проекта Visual Studio помещает проект в решение. По умолчанию имя решения совпадает с именем проекта. Можно изменить имя в **имя решения** поле, но для этого примера оставьте имя по умолчанию.

1. Нажмите кнопку **ОК**, чтобы создать проект.

   Visual Studio создает новое решение и файлы проекта и открывает редактор для Game.cpp файла исходного кода, он создается.

## <a name="organize-projects-and-files"></a>Организации проектов и файлов

Можно использовать **обозревателе решений** для организации и управления проекты, файлы и другие ресурсы в решении.

В этой части пошагового руководства описывается добавление класса в проект. При добавлении класса Visual Studio добавляет соответствующие h и CPP-файлы. Можно просмотреть результаты в **обозревателе решений**.

### <a name="to-add-a-class-to-a-project"></a>Добавление класса в проект

1. Если **обозревателе решений** окно не отображается в Visual Studio в строке меню, выберите **представление > обозреватель решений**.

1. В **обозревателе решений**выберите **игры** проекта. В строке меню выберите **проект > Добавить класс**.

1. В **добавить класс** диалоговое окно, введите *Cardgame* в **имя класса** поле. Не изменяйте имена файлов и параметры по умолчанию. Нажмите кнопку **ОК** .

   Visual Studio создаст новые файлы и добавляет их в проект. Вы увидите их в **обозревателе решений** окна. Файл Cardgame.h и Cardgame.cpp файлы открыты в редакторе.

1. Измените файл Cardgame.h и внести следующие изменения:

   - После открывающей скобки определения класса добавьте два частных элемента данных.
      <!--      [!code-cpp[NVC_Walkthrough_Working_With_Projects#100](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_1.h)] -->

      ```cpp
      int players;
      static int totalParticipants;
      ```

   - Измените конструктор по умолчанию, созданный средой Visual Studio. После спецификатора доступа `public:` найдите строку, которая выглядит следующим образом:

      `Cardgame();`

      Изменить этот конструктор, чтобы принимать один параметр типа `int`с именем *проигрыватели*.

      <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#101](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_2.h)]-->
      `Cardgame(int players);`

   - После деструктора по умолчанию Добавьте встроенное объявление `static int` функция-член с именем *GetParticipants* , не принимает никаких параметров и возвращает `totalParticipants` значение.

      <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#102](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_3.h)]-->
      `static int GetParticipants() { return totalParticipants; }`

   После изменений файл Cardgame.h должен иметь следующий вид:

   <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#103](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_4.h)]-->
   ```cpp
   #pragma once
   class Cardgame
   {
       int players;
       static int totalParticipants;
   public:
       Cardgame(int players);
       ~Cardgame(void);
       static int GetParticipants() { return totalParticipants; }
   };
   ```

   Строка `#pragma once` указывает компилятору включить файл заголовка только один раз. Дополнительные сведения см. в разделе [после](../preprocessor/once.md). Сведения о других ключевых словах C++ в этом файле заголовка см. в разделе [класса](../cpp/class-cpp.md), [int](../cpp/fundamental-types-cpp.md), [статических](../cpp/storage-classes-cpp.md), и [открытый](../cpp/public-cpp.md).

1. Выберите **Cardgame.cpp** вкладки в верхней части области редактирования, чтобы открыть его для редактирования.

1. Удалите весь код в файле и замените его следующим кодом:

   <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#111](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_5.cpp)]-->
   ```cpp
   #include "stdafx.h"
   #include "Cardgame.h"
   #include <iostream>

   using namespace std;

   int Cardgame::totalParticipants = 0;

   Cardgame::Cardgame(int players)
       : players(players)
   {
       totalParticipants += players;
       cout << players << " players have started a new game.  There are now "
            << totalParticipants << " players in total." << endl;
   }

   Cardgame::~Cardgame()
   {
   }
   ```

   > [!NOTE]
   > При вводе кода можно использовать автозавершение. Например, если ввести этот код с клавиатуры, можно ввести *pl* или *tot* и нажмите клавиши Ctrl + Пробел. Функция автозавершения вводит `players` или `totalParticipants` для вас.

## <a name="add-test-code-to-your-main-function"></a>Добавьте код теста в функцию main

Добавьте некоторый код в приложение, который проверяет новые функции.

### <a name="to-add-test-code-to-the-project"></a>Чтобы добавить тестовый код в проект

1. В окне редактора Game.cpp замените существующий код с этим:

   <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#120](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_6.cpp)]-->
   ```cpp
   // Game.cpp : Defines the entry point for the console application.
   //

   #include "stdafx.h"
   #include "Cardgame.h"
   #include <iostream>

   using namespace std;

   void PlayGames()
   {
       Cardgame bridge(4);
       Cardgame blackjack(8);
       Cardgame solitaire(1);
       Cardgame poker(5);
   }

   int main()
   {
       PlayGames();
       return 0;
   }
   ```
Этот код добавляет функцию тестирования `PlayGames`, чтобы исходный код и вызывает его в `main`. 

## <a name="build-and-run-your-app-project"></a>Построение и запуск проекта приложения

Затем постройте проект и запустить приложение.

### <a name="to-build-and-run-the-project"></a>Построение и запуск проекта

1. В строке меню последовательно выберите **Сборка > Собрать решение**.

   Выходные данные построения отображается в **вывода** окна. Если сборка выполнена успешно, выходные данные должны выглядеть следующим образом:

   ```Output
   1>------ Build started: Project: Game, Configuration: Debug Win32 ------
   1>  stdafx.cpp
   1>  Game.cpp
   1>  Cardgame.cpp
   1>  Generating Code...
   1>  Game.vcxproj -> C:\Users\username\Source\Repos\Game\Debug\Game.exe
   ========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
   ```

   **Вывода** окне могут отображаться различные шаги, в зависимости от конфигурации построения, но в случае успешного построения проекта, последняя строка должен выглядеть выводу, приведенному.

   Если сборка завершилась неудаче, сравните свой код в код, который отображается в предыдущих шагах.

1. Чтобы запустить проект, в строке меню, выберите **Отладка > Начать без отладки**. Должно появиться окно консоли и вывод должен выглядеть примерно следующим образом:

   ```Output
   4 players have started a new game.  There are now 4 players in total.
   8 players have started a new game.  There are now 12 players in total.
   1 players have started a new game.  There are now 13 players in total.
   5 players have started a new game.  There are now 18 players in total.
   ```
Нажмите клавишу, чтобы закрыть окно консоли.

Поздравляем, вы успешно построен проект приложения и решения. Дополнительные сведения о построении проектов кода C++ в Visual Studio по-прежнему пошагового руководства.

## <a name="next-steps"></a>Следующие шаги

**Предыдущие:** [использование интегрированной среды разработки Visual Studio для разработки приложений рабочего стола C++](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
**Далее:** [Пошаговое руководство: построение проекта (C++)](../ide/walkthrough-building-a-project-cpp.md).

## <a name="see-also"></a>См. также

[Справочник по языку C++](../cpp/cpp-language-reference.md)  
[Сборка программ C/C++](../build/building-c-cpp-programs.md)