---
title: Обработка исключений (C++/CLI и C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- structured exception handling [C++], managed exceptions
- Exception class, managed applications
- exception handling
- C++ exception handling
- exception handling, types of
- System::Exception class in managed applications
ms.assetid: ccb11fe8-6938-41ac-b477-a183e85865b9
ms.openlocfilehash: b477f7355ee1f4f70a0ad3df8b85c4276c07d397
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "65516579"
---
# <a name="exception-handling--ccli-and-ccx"></a>Обработка исключений (C++/CLI и C++/CX)

В приложениях, скомпилированных с использованием параметра компилятора `/ZW` или `/clr`, для обработки непредвиденных ошибок во время выполнения программы используются *исключения*. В следующих разделах рассматривается обработка исключений в приложениях C++/CX и C++/CLI.

## <a name="in-this-section"></a>В этом разделе

[Основные принципы использования управляемых исключений](../dotnet/basic-concepts-in-using-managed-exceptions.md)<br/>
Описывается создание исключений и использование блоков **try**/**catch**.

[Различия в поведении при обработке исключений в /clr](../dotnet/differences-in-exception-handling-behavior-under-clr.md)<br/>
Рассматриваются отличия от стандартного поведения обработки исключений C++.

[finally](../dotnet/finally.md)<br/>
Описывается использование ключевого слова finally.

[Практическое руководство. Определение и установка глобального обработчика исключений](../dotnet/how-to-define-and-install-a-global-exception-handler.md)<br/>
Демонстрируется захват необработанных исключений.

[Практическое руководство. Перехват исключений в машинном коде, создаваемых MSIL](../dotnet/how-to-catch-exceptions-in-native-code-thrown-from-msil.md)<br/>
Описывается перехват исключений CLR и C++ в машинном коде.

[Практическое руководство. Определение и установка глобального обработчика исключений](../dotnet/how-to-define-and-install-a-global-exception-handler.md)<br/>
Демонстрируется перехват всех необработанных исключений.

## <a name="related-sections"></a>Связанные разделы

[Обработка исключений](../cpp/exception-handling-in-visual-cpp.md)<br/>
Описывается обработка исключений на стандартном языке C++.

## <a name="see-also"></a>См. также

[Расширения компонентов для .NET и UWP](component-extensions-for-runtime-platforms.md)