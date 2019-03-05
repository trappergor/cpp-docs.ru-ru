---
title: Поддержка компоновщика для DLLs, загружаемых с задержкой
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
# <a name="linker-support-for-delay-loaded-dlls"></a>Поддержка компоновщика для DLLs, загружаемых с задержкой

Компоновщик Visual C++ теперь поддерживает отложенную загрузку DLL. Это избавляет вас от необходимости использовать функции пакета SDK для Windows **LoadLibrary** и **GetProcAddress** для реализации отложенной загрузки библиотеки DLL.

До Visual C++ 6.0, единственный способ загрузки библиотеки DLL во время выполнения заключался в использовании **LoadLibrary** и **GetProcAddress**; операционная система загружает библиотеку DLL при исполняемый файл или библиотеку DLL с помощью его загрузки.

Начиная с Visual C++ 6.0, при неявно связывании с библиотекой DLL, компоновщик предоставляет параметры для задержки загрузки библиотеки DLL, пока программа вызывает функцию в этой библиотеке DLL.

Приложение может задержать загрузку DLL при помощи [/DELAYLOAD (Импорт загрузить отложенной)](../../build/reference/delayload-delay-load-import.md) параметр компоновщика со вспомогательной функцией (реализацией по умолчанию, предоставляемой Visual C++). Вспомогательная функция будет загрузить библиотеку DLL во время выполнения путем вызова **LoadLibrary** и **GetProcAddress** для вас.

Необходимо учитывать отложенной загрузке библиотеки DLL, если:

- Программа не может вызвать функцию в DLL.

- Функции в DLL не может вызываться только на поздних этапах выполнения программы.

Отложенная загрузка библиотеки DLL может указываться при построении. EXE-файла или. Проект библиотеки DLL. ОБЪЕКТ. Проект библиотеки DLL, которая задерживает загрузки один или несколько библиотек DLL следует не самому вызывать точки входа, загружаемых с задержкой в Dllmain.

Библиотеки DLL, загружаемые с задержкой в следующих разделах:

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
