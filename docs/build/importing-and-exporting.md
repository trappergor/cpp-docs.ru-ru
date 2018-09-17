---
title: Импорт и экспорт | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], importing
- exporting DLLs [C++]
- importing DLLs [C++]
- DLLs [C++], exporting from
- __declspec(dllimport) keyword [C++]
ms.assetid: 7c44c2aa-2117-4cec-9615-a65bfd3f8f7b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc07ba1de15795e99a5e2ed75a5df9752026d08e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717006"
---
# <a name="importing-and-exporting"></a>Импортирование и экспортирование

Можно импортировать открытые символы в приложение или экспортировать функции из библиотеки DLL с помощью двух методов:

- Использование файла определения модуля (DEF) при построении библиотеки DLL

- Используйте ключевые слова **__declspec(dllimport)** или **__declspec(dllexport)** в определении функции в главном приложении

## <a name="using-a-def-file"></a>С помощью DEF-файла

Файл определения модуля (DEF) — это текстовый файл, содержащий один или несколько операторов модуля, описывающих различные атрибуты библиотеки DLL. Если вы не используете **__declspec(dllimport)** или **__declspec(dllexport)** DEF-файла для экспорта функций библиотеки DLL, необходимой библиотеке DLL.

Можно использовать DEF-файлы для [Импорт в приложение](../build/importing-using-def-files.md) или [Экспорт из библиотеки DLL](../build/exporting-from-a-dll-using-def-files.md).

## <a name="using-declspec"></a>С помощью __declspec

Visual C++ использует **__declspec(dllimport)** и **__declspec(dllexport)** для замены **__export** ключевое слово, используемое ранее в 16-разрядных версиях Visual C++.

Необходимо использовать **__declspec(dllimport)** для кода для компиляции правильно, но это позволяет компилятору создавать лучший код. Компилятор способен создавать лучший код, так как он может определить наличие функции в библиотеке DLL или нет, который позволяет компилятору создавать код, который пропускает уровень косвенного обращения, обычно может присутствовать в вызов функции, которая библиотеке. Тем не менее, необходимо использовать **__declspec(dllimport)** Импорт переменных, используемых в библиотеке DLL.

В разделе EXPORTS файл .def правильное **__declspec(dllexport)** не является обязательным. **__declspec(dllexport)** был добавлен предоставляют простой способ экспорта функций из файла .exe или .dll без использования DEF-файла.

Формат переносимого исполняемого файла Win32 позволяет свести к минимуму число страниц, предназначенных для отладки импортов. Чтобы сделать это, она помещает все адреса импорта по любой программе, в одном месте, именем таблицы адресов импорта. Благодаря этому загрузчик для изменения только одного или двух страниц при доступе к эти операции.

## <a name="what-do-you-want-to-do"></a>Выберите действие

- [Импорт в приложение](../build/importing-into-an-application-using-declspec-dllimport.md)

- [Экспорт из библиотеки DLL](../build/exporting-from-a-dll.md)

## <a name="see-also"></a>См. также

[DLL в Visual C++](../build/dlls-in-visual-cpp.md)