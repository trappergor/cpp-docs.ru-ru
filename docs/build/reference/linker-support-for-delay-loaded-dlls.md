---
title: Поддержка компоновщика для отложенной загрузки DLL
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, linker support
ms.assetid: b2d7e449-2809-42b1-9c90-2c0ca5e31a14
ms.openlocfilehash: 2ff5143b8c3850386f73ff713e7986fdc3b59fd1
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57301393"
---
# <a name="linker-support-for-delay-loaded-dlls"></a>Поддержка компоновщика для отложенной загрузки DLL

Компоновщик Visual C++ теперь поддерживает отложенную загрузку DLL. Это избавляет вас от необходимости использовать функции пакета SDK для Windows **LoadLibrary** и **GetProcAddress** для реализации отложенной загрузки DLL.

До Visual C++ 6.0, единственным способом загрузки DLL во время выполнения было использование **LoadLibrary** и **GetProcAddress**; операционная система загружала DLL при загрузке использовавшего ее исполняемого файла или DLL.

Начиная с Visual C++ 6.0 при неявном связывании с DLL компоновщик предоставляет параметры, позволяющие отложить загрузку DLL до тех пор, пока программа не вызовет функцию из этой DLL.

Приложение может загрузить DLL отложенно, используя параметр компоновщика [/DELAYLOAD (Импорт с отложенной загрузкой)](../../build/reference/delayload-delay-load-import.md) со вспомогательной функцией (реализацией по умолчанию, предоставляемой Visual C++). Вспомогательная функция загрузит DLL во время выполнения, вызвав **LoadLibrary** и **GetProcAddress** для вас.

Рассмотрите возможность использования отложенной загрузки DLL, если:

- Программа может не вызывать функций из DLL.

- Функции из DLL могут вызываться только на поздних этапах выполнения программы.

Отложенную загрузку DLL можно указывать при построении проектов как .EXE, так и .DLL. Проект .DLL, который использует отложенную загрузку для одной или нескольких DLL, не должен сам вызывать загружаемую отложенно точку входа в Dllmain.

Следующие разделы описывают отложенную загрузку DLL:

- [Задание библиотек DLL с отложенной загрузкой](../../build/reference/specifying-dlls-to-delay-load.md)

- [Явная выгрузка библиотеки DLL с отложенной загрузкой](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md)

- [Загрузка всех импортов для библиотеки DLL с отложенной загрузкой](../../build/reference/loading-all-imports-for-a-delay-loaded-dll.md)

- [Привязка Imports](../../build/reference/binding-imports.md)

- [Обработка ошибок и предупреждений](../../build/reference/error-handling-and-notification.md)

- [Сохранение отложенно загружаемых импортированных элементов](../../build/reference/dumping-delay-loaded-imports.md)

- [Ограничения библиотек DLL с отложенной загрузкой](../../build/reference/constraints-of-delay-loading-dlls.md)

- [Понятие вспомогательной функции](understanding-the-helper-function.md)

- [Разработка собственной вспомогательной функции](../../build/reference/developing-your-own-helper-function.md)

## <a name="see-also"></a>См. также

[DLL в Visual C++](../../build/dlls-in-visual-cpp.md)<br/>
[Компоновка](../../build/reference/linking.md)
