---
title: Запуск и завершение программ C++ | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- C++ Standard Library, program startup and termination
- terminating execution
- Function Main procedures
- control text streams
- startup code, and C++ program termination
- main function, program startup
ms.assetid: f72c8f76-f507-4ddd-a270-7b60f4fed625
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f781df914384b553c53e5c42fe16d4c74c9ef99d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="c-program-startup-and-termination"></a>Запуск и завершение программ C++

Программы на языке C++ выполняет те же операции, что и программы на языке C при запуске программы и при завершении программы, а также несколько дополнительных операций, описанных здесь.

Перед вызовом целевой средой функции `main` и после сохранения всех константных начальных значений, указанных вами во всех объектах, имеющих статическую длительность, программа выполняет все оставшиеся конструкторы для таких статических объектов. Порядок выполнения разных записей преобразования не указан, но тем не менее можно предположить, что некоторые объекты [iostreams](../standard-library/iostreams-conventions.md) правильно инициализированы для использования этими статическими конструкторами. Это следующие управляющие текстовые потоки.

- [cin](../standard-library/iostream.md#cin) — для стандартного ввода.

- [cout](../standard-library/iostream.md#cout) — для стандартного вывода.

- [cerr](../standard-library/iostream.md#cerr) — для стандартного вывода ошибки без буферизации.

- [clog](../standard-library/iostream.md#clog) — для стандартного вывода ошибки буферизацией.

Эти объекты также можно использовать в деструкторах, вызываемых для статических объектов, во время завершения программы.

Как и в C, возврат из `main` или вызов `exit` вызывает все функции, зарегистрированные с `atexit`, в обратном порядке из реестра. Исключение, созданное такой зарегистрированной функцией, вызывает `terminate`.

## <a name="see-also"></a>См. также

[Общие сведения о стандартной библиотеке C++](../standard-library/cpp-standard-library-overview.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
