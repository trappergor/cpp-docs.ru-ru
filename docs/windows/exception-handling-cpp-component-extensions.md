---
title: Обработка исключений (расширения компонентов C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- structured exception handling [C++], managed exceptions
- Exception class, managed applications
- exception handling
- C++ exception handling
- exception handling, types of
- System::Exception class in managed applications
ms.assetid: ccb11fe8-6938-41ac-b477-a183e85865b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2213266d281933c6a6a59775584532acaeb39d6e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46412333"
---
# <a name="exception-handling--c-component-extensions"></a>Обработка исключений (расширения компонентов C++)

Приложения, скомпилированные с `/ZW` параметр компилятора или `/clr` используются *исключения* для обработки непредвиденных ошибок во время выполнения программы. В следующих разделах рассматривается обработка исключений в приложениях C++/CX и C++/CLI.

## <a name="in-this-section"></a>В этом разделе

[Основные принципы использования управляемых исключений](../dotnet/basic-concepts-in-using-managed-exceptions.md)<br/>
Описывает создание исключений и использование **попробуйте**/**catch** блоков.

[Различия в поведении в/CLR при обработке исключений](../dotnet/differences-in-exception-handling-behavior-under-clr.md)<br/>
Рассматриваются отличия от стандартного поведения обработки исключений C++.

[finally](../dotnet/finally.md)<br/>
Описывается использование ключевого слова finally.

[Практическое руководство. Определение и установка глобального обработчика исключений](../dotnet/how-to-define-and-install-a-global-exception-handler.md)<br/>
Демонстрируется захват необработанных исключений.

[Практическое руководство. Исключения в машинном коде, создаваемые MSIL](../dotnet/how-to-catch-exceptions-in-native-code-thrown-from-msil.md)<br/>
Описывается перехват исключений CLR и C++ в машинном коде.

[Практическое руководство. Определение и установка глобального обработчика исключений](../dotnet/how-to-define-and-install-a-global-exception-handler.md)<br/>
Демонстрируется перехват всех необработанных исключений.

## <a name="related-sections"></a>Связанные разделы

[Обработка исключений](../cpp/exception-handling-in-visual-cpp.md)<br/>
Описывается обработка исключений в C++.

## <a name="see-also"></a>См. также

[Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)