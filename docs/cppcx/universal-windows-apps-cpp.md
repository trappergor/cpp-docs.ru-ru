---
title: Универсальные приложения Windows (C++)
ms.date: 03/30/2018
ms.assetid: 357121cc-d390-4bae-b34a-39614861a9f4
ms.topic: overview
ms.openlocfilehash: 45d02a5ab923ee46da97d78a1e5ceb2f4313352a
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841679"
---
# <a name="universal-windows-apps-c"></a>Универсальные приложения Windows (C++)

Универсальная платформа Windows (UWP) — это современный интерфейс программирования для Windows. С помощью UWP вы пишете приложение или компонент один раз и развертываете его на любом устройстве Windows 10. Можно написать компонент на C++, а приложения, написанные на любом другом языке, совместимом с UWP, могут использовать его.

Большая часть документации по UWP находится в дереве содержимого Windows в [документации по универсальная платформа Windows](/windows/uwp/). Здесь вы найдете начальные учебники, а также справочную документацию.

Для новых приложений и компонентов UWP рекомендуется использовать [c++/WinRT](/windows/uwp/cpp-and-winrt-apis/)— новую стандартную проекцию c++ 17 для Среда выполнения Windows API. C++/WinRT доступна в пакете SDK для Windows 10, начиная с версии 1803. C++/WinRT реализована полностью в файлах заголовков и предназначена для предоставления доступа к современным API Windows через первый класс. В отличие от реализации C++/CX, C++/WinRT не использует нестандартный синтаксис или расширения языка Майкрософт и использует все преимущества компилятора C++ для создания высокооптимизированных выходных данных. Дополнительные сведения см. [в статье Введение в C++/WinRT](/windows/uwp/cpp-and-winrt-apis/intro-to-using-cpp-with-winrt).

Чтобы упаковать имеющееся настольное приложение для развертывания с помощью Microsoft Store, можно использовать конвертор приложений Desktop Bridge. Дополнительные сведения см. [в разделе Использование среды выполнения Visual C++ в проектах Centennial](https://devblogs.microsoft.com/cppblog/using-visual-c-runtime-in-centennial-project/) и [Desktop Bridge](/windows/uwp/porting/desktop-to-uwp-root).

## <a name="uwp-apps-that-use-ccx"></a>Приложения UWP, использующие C++/CX

[Справочник по языку C++/CX](visual-c-language-reference-c-cx.md)\
Описывает набор расширений, упрощающих использование C++ среда выполнения Windows API и разрешающее обработку ошибок, основанную на исключениях.

[Создание приложений и библиотек (C++/CX)](building-apps-and-libraries-c-cx.md)\
Описание создания библиотек DLL и статических библиотек, доступных из приложения или компонента C++/CX.

[Учебник. Создание приложения "Hello, World" для UWP в C++/CX](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)\
Пошаговое руководство, в котором представлены основные понятия разработки приложений UWP в C++/CX.

[Создание среда выполнения Windows компонентов в C++/CX](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)\
Описывает создание библиотек DLL, которые могут использовать другие приложения и компоненты UWP.

[Программирование игр UWP](/windows/uwp/gaming/)\
Описывает, как использовать DirectX и C++/CX для создания игр.

## <a name="uwp-apps-that-use-the-windows-runtime-c-template-library-wrl"></a>Приложения UWP, использующие библиотеку шаблонов среда выполнения Windows C++ (WRL)

Библиотека шаблонов среда выполнения Windows C++ предоставляет низкоуровневые COM-интерфейсы, с помощью которых код C++ ISO может получить доступ к среда выполнения Windows в среде без исключений. В большинстве случаев рекомендуется использовать C++/WinRT или C++/CX вместо библиотеки шаблонов C++ среда выполнения Windows для разработки приложений UWP. Дополнительные сведения о библиотеке шаблонов среда выполнения Windows C++ см. в разделе [Библиотека шаблонов c++ среда выполнения Windows (WRL)](wrl/windows-runtime-cpp-template-library-wrl.md).

## <a name="see-also"></a>См. также раздел

[C++ в Visual Studio](../overview/visual-cpp-in-visual-studio.md)<br/>
[Общие сведения о программировании Windows в C++](../windows/overview-of-windows-programming-in-cpp.md)<br/>
