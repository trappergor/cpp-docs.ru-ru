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
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328519"
---
# <a name="importing-and-exporting-inline-functions"></a>Импорт и экспорт встраиваемых функций

Импортированные функции можно определить как встроенные. Результат примерно такой же, как и при определении стандартной встроенной функции. Вызовы функции разворачиваются во встроенном коде во многом аналогично макросу. Это полезно в качестве способа поддержки классов C++ в библиотеке DLL, которые могут встраивать некоторые функции-члены для повышения эффективности.

Одна из функций импортированной встроенной функции заключается в том, что ее адрес можно получить в C++. Компилятор возвращает адрес копии встроенной функции, размещенной в библиотеке DLL. Еще одна функция импортированных встроенных функций заключается в том, что можно инициализировать статические локальные данные импортированной функции, в отличие от глобальных импортированных данных.

> [!CAUTION]
> Следует быть внимательными при предоставлении импортированных встроенных функций, поскольку они могут создать вероятность конфликтов версий. Встроенная функция расширяется в код приложения; поэтому при последующей перезаписи функции она не обновляется, пока не будет перекомпилировано само приложение. (Как правило, функции DLL могут обновляться без перестроения приложений, которые их используют.)

## <a name="what-do-you-want-to-do"></a>Выберите действие

- [Экспорт из библиотеки DLL](exporting-from-a-dll.md)

- [Экспорт из библиотеки DLL с использованием DEF-файлов](exporting-from-a-dll-using-def-files.md)

- [Экспорт из библиотеки DLL с использованием __declspec(dllexport)](exporting-from-a-dll-using-declspec-dllexport.md)

- [Экспорт и импорт с использованием AFX_EXT_CLASS](exporting-and-importing-using-afx-ext-class.md)

- [Экспорт функций на языке C++ для использования в исполняемых модулях, исходный код которых написан на языке C](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [Определение подходящего способа экспорта](determining-which-exporting-method-to-use.md)

- [Импорт в приложение с помощью __declspec(dllimport)](importing-into-an-application-using-declspec-dllimport.md)

## <a name="see-also"></a>См. также

[Импортирование и экспортирование](importing-and-exporting.md)
