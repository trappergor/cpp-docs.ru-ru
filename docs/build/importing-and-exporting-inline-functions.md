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
ms.openlocfilehash: abb0443ab8fbd315524350caaff34e0250147ed2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328519"
---
# <a name="importing-and-exporting-inline-functions"></a>Импорт и экспорт встраиваемых функций

Импортные функции могут быть определены как вливые. Эффект примерно такой же, как определение стандартной функции в строке; вызовы в функцию расширяются в рядный код, так же, как макрос. Это в основном полезно в качестве способа поддержки классов СЗ в DLL, которые могут привести к линии некоторых из их функций-членов для эффективности.

Одной из особенностей импортируемой вневодной функции является то, что вы можете взять ее адрес в СЗ. Компилятор возвращает адрес копии вневательной функции, проживающей в DLL. Еще одной особенностью импортированных внеочередных функций является то, что можно инициализировать статические локальные данные импортируемой функции, в отличие от глобальных импортируемых данных.

> [!CAUTION]
> Вы должны проявлять осторожность при предоставлении импортных влинейных функций, поскольку они могут создавать возможность конфликтов версий. Вневливая функция расширяется в код приложения; поэтому, если позже переписать функцию, она не будет обновлена, если само приложение не будет перекомпилировано. (Обычно функции DLL могут обновляться без восстановления приложений, которые их используют.)

## <a name="what-do-you-want-to-do"></a>Выбор действия

- [Экспорт из DLL](exporting-from-a-dll.md)

- [Экспорт из DLL с использованием . Файлы DEF](exporting-from-a-dll-using-def-files.md)

- [Экспорт из DLL с использованием __declspec (dllexport)](exporting-from-a-dll-using-declspec-dllexport.md)

- [Экспорт и импорт с использованием AFX_EXT_CLASS](exporting-and-importing-using-afx-ext-class.md)

- [Экспортные функции СЗЗ для использования в исполнителях C-языка](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [Определение подходящего способа экспорта](determining-which-exporting-method-to-use.md)

- [Импорт в приложение с помощью __declspec(dllimport)](importing-into-an-application-using-declspec-dllimport.md)

## <a name="see-also"></a>См. также раздел

[Импорт и экспорт](importing-and-exporting.md)
