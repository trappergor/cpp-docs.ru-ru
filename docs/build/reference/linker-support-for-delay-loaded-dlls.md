---
title: Поддержка компоновщика для отложенной загрузки DLL
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, linker support
ms.assetid: b2d7e449-2809-42b1-9c90-2c0ca5e31a14
ms.openlocfilehash: b6e514a6b13aced4fcd765df091810504f948588
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62176256"
---
# <a name="linker-support-for-delay-loaded-dlls"></a>Поддержка компоновщика для отложенной загрузки DLL

Компоновщик MSVC теперь поддерживает отложенную загрузку DLL. Это избавляет вас от необходимости использовать функции пакета SDK для Windows **LoadLibrary** и **GetProcAddress** для реализации отложенной загрузки DLL.

До версии Visual C++ 6.0 единственным способом загрузки DLL во время выполнения было использование **LoadLibrary** и **GetProcAddress**; операционная система загружала DLL при загрузке использовавшего ее исполняемого файла или DLL.

Начиная с Visual C++ 6.0 при неявном связывании с DLL компоновщик предоставляет параметры, позволяющие отложить загрузку DLL до тех пор, пока программа не вызовет функцию из этой DLL.

Приложение может загрузить DLL отложенно, используя параметр компоновщика [/DELAYLOAD (Импорт с отложенной загрузкой)](delayload-delay-load-import.md) со вспомогательной функцией (реализацией по умолчанию, предоставляемой Visual C++). Вспомогательная функция загрузит DLL во время выполнения, вызвав **LoadLibrary** и **GetProcAddress**.

Рассмотрите возможность использования отложенной загрузки DLL, если:

- Программа может не вызывать функций из DLL.

- Функции из DLL могут вызываться только на поздних этапах выполнения программы.

Отложенную загрузку DLL можно указывать при сборке проектов как .EXE, так и .DLL. Проект .DLL, который использует отложенную загрузку для одной или нескольких DLL, не должен сам вызывать загружаемую отложенно точку входа в Dllmain.

Следующие разделы описывают отложенную загрузку DLL:

- [Задание библиотек DLL с отложенной загрузкой](specifying-dlls-to-delay-load.md)

- [Явная выгрузка библиотеки DLL с отложенной загрузкой](explicitly-unloading-a-delay-loaded-dll.md)

- [Загрузка всех импортов для библиотеки DLL с отложенной загрузкой](loading-all-imports-for-a-delay-loaded-dll.md)

- [Привязка Imports](binding-imports.md)

- [Обработка ошибок и предупреждений](error-handling-and-notification.md)

- [Сохранение отложенно загружаемых импортированных элементов](dumping-delay-loaded-imports.md)

- [Ограничения библиотек DLL с отложенной загрузкой](constraints-of-delay-loading-dlls.md)

- [Понятие вспомогательной функции](understanding-the-helper-function.md)

- [Разработка собственной вспомогательной функции](developing-your-own-helper-function.md)

## <a name="see-also"></a>См. также

[DLL в Visual C++](../dlls-in-visual-cpp.md)<br/>
[Справочник по компоновщику MSVC](linking.md)
