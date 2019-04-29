---
title: Импорт и экспорт встраиваемых функций
ms.date: 11/04/2016
helpviewer_keywords:
- exporting functions [C++], inline functions
- inline functions [C++], importing
- DLLs [C++], importing
- importing functions [C++]
- DLLs [C++], exporting from
- importing inline functions [C++]
- inline functions [C++], exporting
- functions [C++], importing
- functions [C++], exporting
ms.assetid: 89f488f8-b078-40fe-afd7-80bd7840057b
ms.openlocfilehash: ed523d84228124d4a8d99e443c0c744f362f1c56
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273447"
---
# <a name="importing-and-exporting-inline-functions"></a>Импорт и экспорт встраиваемых функций

Импортируемых функций можно определить как встроенные. Действует примерно так же, как определение стандартной встроенной функции; вызовы функции будут развернуты во встроенный код, как макрос. Это часто полезно в тех случаях, как средства поддержки C++ классы в библиотеке DLL, могут встраиваться некоторые члены функции для повышения эффективности.

Одной из особенностей импортируемой встроенной функции является то, что можно получить его адрес в C++. Компилятор возвращает адрес копии встроенной функции, находящейся в библиотеке DLL. Другой особенностью импортированных встроенных функций является возможность инициализации статических локальных данных импортируемой функции, в отличие от глобальных импортируемых данных.

> [!CAUTION]
>  Следует соблюдать осторожность при передаче импортируемых встроенных функций, так как они могут вызвать конфликты версий. Встроенная функция разворачивается в код приложения; Таким образом Если позже вы повторное написание функции, она не обновится, если не перекомпилируется само приложение. (Как правило, функции DLL могут обновляться без повторной сборки приложения, которые их используют.)

## <a name="what-do-you-want-to-do"></a>Выберите действие

- [Экспорт из библиотеки DLL](exporting-from-a-dll.md)

- [Экспорт из библиотеки DLL с помощью. DEF-файлы](exporting-from-a-dll-using-def-files.md)

- [Экспорт из библиотеки DLL с использованием __declspec(dllexport)](exporting-from-a-dll-using-declspec-dllexport.md)

- [Экспорт и импорт с использованием AFX_EXT_CLASS](exporting-and-importing-using-afx-ext-class.md)

- [Экспорт функций C++ для использования в исполняемых файлах языка C](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [Определение подходящего метода экспорта для использования](determining-which-exporting-method-to-use.md)

- [Импорт в приложение с помощью __declspec(dllimport)](importing-into-an-application-using-declspec-dllimport.md)

## <a name="see-also"></a>См. также

[Импортирование и экспортирование](importing-and-exporting.md)
