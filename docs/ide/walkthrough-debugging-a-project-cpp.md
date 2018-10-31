---
title: Пошаговое руководство. Отладка проекта (C++) | Документы Майкрософт
ms.custom: ''
ms.date: 09/14/2018
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
ms.openlocfilehash: bd8d0cebc34b8f0d59f54e720d6a37a52ab2d9e9
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50069325"
---
# <a name="walkthrough-debugging-a-project-c"></a>Пошаговое руководство. Отладка проекта (C++)

В этом пошаговом руководстве рассматривается изменение программы для устранения проблемы, обнаруженной при проверке проекта.

## <a name="prerequisites"></a>Предварительные требования

- Это пошаговое руководство предполагает знание основ языка C++.

- В нем также предполагается, что вы выполнили инструкции из предыдущих руководств, перечисленных в статье [Использование интегрированной среды разработки Visual Studio для разработки приложений для настольных систем на языке C++](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).

### <a name="to-fix-a-program-that-has-a-bug"></a>Исправление программы с ошибкой

1. Чтобы узнать, что происходит при уничтожении объекта `Cardgame`, просмотрите деструктор класса `Cardgame`.

   В строке меню выберите **Вид** > **Представление классов**.

   В окне **Представление классов** разверните дерево проекта **Game** и выберите класс **Cardgame** для отображения его членов и методов.

   Откройте контекстное меню для деструктора **~Cardgame(void)** и выберите **Перейти к определению**.

1. Чтобы уменьшить `totalParticipants` при завершении Cardgame, добавьте приведенный ниже код между открывающей и закрывающей фигурными скобками деструктора `Cardgame::~Cardgame`.

   [!code-cpp[NVC_Walkthrough_Debugging_A_Project#110](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_1.cpp)]

1. После изменений файл Cardgame.cpp должен содержать примерно такой код:

   [!code-cpp[NVC_Walkthrough_Debugging_A_Project#111](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_2.cpp)]

1. В строке меню последовательно выберите **Сборка**  >  **Собрать решение**.

1. После завершения сборки запустите ее в режиме отладки, выбрав **Отладка** > **Начать отладку** в строке меню или нажав клавишу **F5**. Программа останавливается в первой точке останова.

1. Для пошагового выполнения программы в строке меню выберите **Отладка** > **Шаг с обходом** или нажмите клавишу **F10**.

   Обратите внимание, что после каждого выполнения конструктора `Cardgame` значение `totalParticipants` увеличивается. Когда функция `PlayGames` возвращает значение, так как каждый экземпляр `Cardgame` выходит за пределы области и удаляется (и вызывается деструктор), значение `totalParticipants` уменьшается. Непосредственно перед выполнением оператора `return` значение `totalParticipants` равно нулю.

1. Продолжайте пошаговое выполнение программы до ее завершения или позвольте ей выполняться, выбрав **Отладка** > **Выполнить** в строке меню или нажав клавишу **F5**.

## <a name="next-steps"></a>Следующие шаги

**Предыдущая статья:** [Пошаговое руководство. Тестирование проекта (C++)](../ide/walkthrough-testing-a-project-cpp.md)<br/>
**Следующая статья:** [Пошаговое руководство. Развертывание программы (C++)](../ide/walkthrough-deploying-your-program-cpp.md)<br/>

## <a name="see-also"></a>См. также

[Справочник по языку C++](../cpp/cpp-language-reference.md)<br/>
[Сборка программ C/C++](../build/building-c-cpp-programs.md)<br/>
