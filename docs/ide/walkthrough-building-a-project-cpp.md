---
title: Пошаговое руководство. Сборка проекта (C++) | Документы Майкрософт
ms.custom: ''
ms.date: 09/14/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- building projects [C++]
- projects [C++], building
- project building [C++]
ms.assetid: d459bc03-88ef-48d0-9f9a-82d17f0b6a4d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3071b779338150816cb1d52d16932ac0e3878538
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50079328"
---
# <a name="walkthrough-building-a-project-c"></a>Пошаговое руководство. Построение проекта (C++)

В этом пошаговом руководстве в код на языке Visual C++ умышленно вводится синтаксическая ошибка, чтобы ознакомиться с тем, как проявляется ошибка компиляции и как ее можно исправить. При компиляции проекта выдается сообщение об ошибке, указывающее на ее характер и место возникновения.

## <a name="prerequisites"></a>Предварительные требования

- Это пошаговое руководство предполагает знание основ языка C++.

- В нем также предполагается, что вы выполнили инструкции из предыдущих руководств, перечисленных в статье [Использование интегрированной среды разработки Visual Studio для разработки приложений для настольных систем на языке C++](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).

### <a name="to-fix-compilation-errors"></a>Исправление ошибок компиляции

1. В файле Game.cpp удалите точку с запятой в последней строке, чтобы она выглядела как эта инструкция:

    `return 0`

1. В строке меню последовательно выберите **Сборка**  >  **Собрать решение**.

1. Сообщение в окне **Список ошибок** показывает, что при сборке проекта произошла ошибка. Описание ошибки представлено в виде следующего сообщения об ошибке:

    `error C2143: syntax error: missing ';' before '}'`

  Чтобы просмотреть справочные сведения об этой ошибке, выделите ее в окне **Список ошибок** и нажмите клавишу **F1**.

1. Верните точку с запятой в конец строки с синтаксической ошибкой:

   `return 0;`

1. В строке меню последовательно выберите **Сборка**  >  **Собрать решение**.

  Сообщение в окне **Выходные данные** указывает, что проект успешно скомпилирован.

    ```Output
    1>------ Build started: Project: Game, Configuration: Debug Win32 ------
    1>Game.cpp
    1>Game.vcxproj -> C:\Users\<username>\source\repos\Game\Debug\Game.exe
    ========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
    ```

## <a name="next-steps"></a>Следующие шаги

**Предыдущая статья.** [Пошаговое руководство. Работа с проектами и решениями (C++)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md)<br/>
**Следующая статья.** [Пошаговое руководство. Тестирование проекта (C++)](../ide/walkthrough-testing-a-project-cpp.md)<br/>

## <a name="see-also"></a>См. также

[Справочник по языку C++](../cpp/cpp-language-reference.md)<br/>
[Сборка программ C/C++](../build/building-c-cpp-programs.md)<br/>
