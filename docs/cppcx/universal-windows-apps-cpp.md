---
title: Универсальные приложения Windows (C++)
ms.date: 03/30/2018
ms.assetid: 357121cc-d390-4bae-b34a-39614861a9f4
ms.topic: landing-page
ms.openlocfilehash: 68952e93e4f91ac3653a9991802ad42854d9d25a
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70741034"
---
# <a name="universal-windows-apps-c"></a>Универсальные приложения Windows (C++)

Универсальная платформа Windows (UWP) — это современный интерфейс программирования для Windows. С помощью UWP вы пишете приложение или компонент один раз и развертываете его на любом устройстве Windows 10. Вы можете написать компонент в C++ , а приложения, написанные на любом другом языке, совместимом с UWP, могут использовать его.

Большая часть документации по UWP находится в дереве содержимого Windows в [документации по универсальная платформа Windows](/windows/uwp/). Здесь вы найдете начальные учебники, а также справочную документацию. 

Для новых приложений и компонентов UWP рекомендуется использовать [ C++/WinRT](/windows/uwp/cpp-and-winrt-apis/)— новую стандартную проекцию c++ 17 для Среда выполнения Windows API. C++/WinRT доступен в пакете SDK для Windows 10 из версии 1803. C++/WinRT реализован полностью в файлах заголовков и предназначен для предоставления доступа к современным API Windows через первый класс. В отличие от C++реализации в/CX. C++/WinRT не использует нестандартный синтаксис или расширения языка Майкрософт и использует все преимущества C++ компилятора для создания высокооптимизированных выходных данных. Дополнительные сведения см. [в статье Введение C++в/WinRT](/windows/uwp/cpp-and-winrt-apis/intro-to-using-cpp-with-winrt).

Чтобы упаковать имеющееся настольное приложение для развертывания с помощью Microsoft Store, можно использовать конвертор приложений Desktop Bridge. Дополнительные сведения см. [в статье Использование C++ Visual Runtime в Centennial Project](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project) и [Desktop Bridge](/windows/uwp/porting/desktop-to-uwp-root).

## <a name="uwp-apps-that-use-ccx"></a>Приложения UWP, использующие C++/CX

|||
|-|-|
|[C++Справочник по языку/CX](visual-c-language-reference-c-cx.md)|Описывает набор расширений, упрощающих C++ использование среда выполнения Windows интерфейсов API и обеспечивающих обработку ошибок, основанную на исключениях.|
|[Построение приложений и библиотек (C++/CX)](building-apps-and-libraries-c-cx.md)|Описание создания библиотек DLL и статических библиотек, доступных из приложения или компонента C++/CX.|
|[Учебник. Создание приложения "Hello, World" для UWP в C++/CX](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)|Пошаговое руководство, в котором представлены основные понятия разработки приложений C++UWP в/CX. |
|[Создание компонентов среда выполнения Windows в C++/CX](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)|Описывает создание библиотек DLL, которые могут использовать другие приложения и компоненты UWP.|
|[Программирование игр UWP](/windows/uwp/gaming/)|Описание использования DirectX и C++/CX для создания игр.|

## <a name="uwp-apps-that-use-the-windows-runtime-c-template-library-wrl"></a>Приложения UWP, использующие библиотеку шаблонов C++ среда выполнения Windows (WRL)

Библиотека шаблонов C++ среда выполнения Windows предоставляет низкоуровневые COM-интерфейсы, по которым код ISO C++ может получить доступ к среда выполнения Windows в среде без исключений. В большинстве случаев рекомендуется использовать C++/WinRT или C++/cx вместо библиотеки шаблонов среда выполнения Windows C++ для разработки приложений UWP. Сведения о библиотеке шаблонов среда выполнения Windows C++ см. в разделе [Библиотека C++ шаблонов среда выполнения Windows (WRL)](wrl/windows-runtime-cpp-template-library-wrl.md).

## <a name="see-also"></a>См. также

[C++ в Visual Studio](../overview/visual-cpp-in-visual-studio.md)<br/>
[Общие сведения о программировании на C++ в Windows](../windows/overview-of-windows-programming-in-cpp.md)<br/>