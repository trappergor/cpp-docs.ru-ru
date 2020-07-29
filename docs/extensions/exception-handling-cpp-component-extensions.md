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
ms.openlocfilehash: 23d65bb8056672d12e3d40f9fcab1e58bab65a3d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219707"
---
# <a name="exception-handling--ccli-and-ccx"></a>Обработка исключений (C++/CLI и C++/CX)

В приложениях, скомпилированных с использованием параметра компилятора `/ZW` или `/clr`, для обработки непредвиденных ошибок во время выполнения программы используются *исключения*. В следующих разделах рассматривается обработка исключений в приложениях C++/CX и C++/CLI.

## <a name="in-this-section"></a>в этом разделе

[Основные понятия, связанные с использованием управляемых исключений](../dotnet/basic-concepts-in-using-managed-exceptions.md)<br/>
Описывает создание исключений и использование **`try`** / **`catch`** блоков.

[Различия в поведении обработки исключений в/CLR](../dotnet/differences-in-exception-handling-behavior-under-clr.md)<br/>
Рассматриваются отличия от стандартного поведения обработки исключений C++.

[finally](../dotnet/finally.md)<br/>
Описывается использование ключевого слова finally.

[Как определить и установить глобальный обработчик исключений](../dotnet/how-to-define-and-install-a-global-exception-handler.md)<br/>
Демонстрируется захват необработанных исключений.

[Инструкции. перехват исключений в машинном коде, созданном из MSIL](../dotnet/how-to-catch-exceptions-in-native-code-thrown-from-msil.md)<br/>
Описывается перехват исключений CLR и C++ в машинном коде.

[Как определить и установить глобальный обработчик исключений](../dotnet/how-to-define-and-install-a-global-exception-handler.md)<br/>
Демонстрируется перехват всех необработанных исключений.

## <a name="related-sections"></a>Связанные разделы

[Обработка исключений](../cpp/exception-handling-in-visual-cpp.md)<br/>
Описывается обработка исключений на стандартном языке C++.

## <a name="see-also"></a>См. также раздел

[Расширения компонентов для .NET и UWP](component-extensions-for-runtime-platforms.md)
