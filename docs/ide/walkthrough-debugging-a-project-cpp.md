---
title: Пошаговое руководство. Отладка проекта (C++) | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- projects [C++], debugging
- project debugging [C++]
- debugging projects
ms.assetid: a5cade77-ba51-4b03-a7a0-6897e3cd6a59
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ecfda5e2549b3aa9be1f0471e301cc2a21c6fd5a
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "33340038"
---
# <a name="walkthrough-debugging-a-project-c"></a>Пошаговое руководство. Отладка проекта (C++)
Это пошаговое руководство рассматривает изменение программы для устранения проблемы, обнаруженной при проверке проекта.  
  
## <a name="prerequisites"></a>Предварительные требования  
  
-   Это пошаговое руководство предполагает знание основ языка C++.  
  
-   В нем также предполагается, что вы выполнили ранее описанные пошаговые руководства, перечисленные в разделе [Использование интегрированной среды разработки Visual Studio для разработки классических приложений на языке C++](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
  
### <a name="to-fix-a-program-that-has-a-bug"></a>Исправление программы с ошибкой  
  
1.  Чтобы узнать, что происходит при уничтожении объекта `Cardgame`, просмотрите деструктор класса `Cardgame`.  
  
     В строке меню выберите **Вид** и **Представление классов**.  
  
     В окне **Представление классов** разверните дерево проекта **Game** и выберите класс **Cardgame** для отображения его членов и методов.  
  
     Откройте контекстное меню для деструктора **~Cardgame(void)** и выберите **Перейти к определению**.  
  
2.  Чтобы уменьшить `totalParticipants` при завершении Cardgame, добавьте приведенный ниже код между открывающей и закрывающей фигурными скобками деструктора `Cardgame::~Cardgame`.  
  
     [!code-cpp[NVC_Walkthrough_Debugging_A_Project#110](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_1.cpp)]  
  
3.  После изменений файл Cardgame.cpp должен иметь следующий вид:  
  
     [!code-cpp[NVC_Walkthrough_Debugging_A_Project#111](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_2.cpp)]  
  
4.  В строке меню последовательно выберите **Сборка**и **Собрать решение**.  
  
5.  После завершения сборки запустите ее в режиме отладки, выбрав **Отладка** и **Начать отладку** в строке меню или нажав клавишу F5. Программа останавливается в первой точке останова.  
  
6.  Для пошагового выполнения программы в строке меню выберите **Отладка** и **Шаг с обходом** или нажмите клавишу F10.  
  
     Обратите внимание, что после каждого выполнения конструктора Cardgame значение `totalParticipants` увеличивается. Когда функция `PlayGames` возвращает значение, так как каждый экземпляр Cardgame выходит за пределы области и удаляется (и вызывается деструктор), значение `totalParticipants` уменьшается. Непосредственно перед выполнением оператора `return` значение `totalParticipants` равно нулю.  
  
7.  Продолжайте пошаговое выполнение программы до ее завершения или позвольте ей выполняться, выбрав **Отладка** и **Выполнить** в строке меню или нажав клавишу F5.  
  
## <a name="next-steps"></a>Следующие шаги  
 **Предыдущий:** [Пошаговое руководство. Тестирование проекта (C++)](../ide/walkthrough-testing-a-project-cpp.md) &#124; **Следующий:**[Пошаговое руководство. Развертывание программы (C++)](../ide/walkthrough-deploying-your-program-cpp.md)  
  
## <a name="see-also"></a>См. также  
 [Справочник по языку C++](../cpp/cpp-language-reference.md)   
 [Сборка программ C/C++](../build/building-c-cpp-programs.md)