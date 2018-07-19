---
title: Универсальные приложения Windows (C++) | Документы Microsoft
ms.custom: ''
ms.date: 03/30/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 357121cc-d390-4bae-b34a-39614861a9f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9914e9ac83efcc43ef120259254b65ef4f1e0ee9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891127"
---
# <a name="universal-windows-apps-c"></a>Универсальные приложения Windows (C++)

Универсальные приложения для платформы Windows (UWP) реализуют набор принципов разработки, выделяющих простые пользовательские интерфейсы, организованные вокруг содержимого, которое автоматически настраивается в соответствии с различными размерами экранов на разных устройствах. Для создания пользовательского интерфейса используется разметка XAML, а для кода — неуправляемый код C++. Можно также создавать компоненты (DLL), которые могут применяться приложениями UWP, написанными на других языках. Область API для приложений UWP представляет среду выполнения Windows, которая является хорошо организованную библиотеку, которая предоставляет широкий набор служб для операционной системы.

> [!TIP]  
> Для Windows 10 можно использовать преобразователь приложения рабочего стола моста упаковка существующего приложения рабочего стола для развертывания с помощью Microsoft Store. Дополнительные сведения см. в разделе [с помощью среды выполнения Visual C++ в проекте Centennial](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project) и [мост Desktop](/windows/uwp/porting/desktop-to-uwp-root).

## <a name="uwp-apps-that-use-cwinrt"></a>Приложения UWP, использующие C + +/ WinRT

C + +/ WinRT является новый, доступный только для заголовка на основе библиотеки C++ языка проекции для среды выполнения Windows, который использует полностью стандартный язык C++, в отличие от C + +/ CX реализации. C + +/ WinRT не использует нестандартный синтаксис или расширения языка корпорации Майкрософт, а также полностью использует компилятор C++ для создания выходного файла с высокой степенью оптимизации. Дополнительные сведения см. в разделе [C + +/ WinRT](/windows/uwp/cpp-and-winrt-apis). Введение в C + +/ WinRT и примеры кода см. [введение в C + +/ WinRT](/windows/uwp/cpp-and-winrt-apis/intro-to-using-cpp-with-winrt).

## <a name="uwp-apps-that-use-ccx"></a>Приложения UWP, использующие C + +/ CX

|||
|-|-|
|[Справочник по языку Visual C++ (C++/CX)](../cppcx/visual-c-language-reference-c-cx.md)|Описание набора расширений, которые упрощают использование интерфейсов API среды выполнения Windows C++ и обеспечивают обработку ошибок, основанную на исключениях.|
|[Построение приложений и библиотек (C++/CX)](../cppcx/building-apps-and-libraries-c-cx.md)|Описание создания библиотек DLL и статических библиотек, доступных из приложения или компонента C++/CX.|
|[Учебник: Создание UWP приложение «Hello, World» в C + +/ CX](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)|Пошаговое руководство, представляющее основные понятия разработки приложений UWP в C + +/ CX. |
|[Создание компонентов среды выполнения Windows в C + +/ CX](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)|Описание создания библиотек DLL, которые можно использовать в других приложениях UWP и компонентов.|
|[Программирование игры UWP](/windows/uwp/gaming/)|Описывает способы использования DirectX и C + +/ CX для создания игр.|

## <a name="uwp-apps-that-use-the-windows-runtime-c-template-library-wrl"></a>Приложения UWP, использующие библиотека шаблонов C++ среды выполнения Windows (WRL)

Библиотека шаблонов C++ среды выполнения Windows предоставляет низкоуровневые интерфейсы COM, с помощью которых код C++ стандарта ISO может обращаться к среды выполнения Windows в среде без поддержки исключений. В большинстве случаев рекомендуется использовать C + +/ WinRT или C + +/ CX вместо библиотека шаблонов C++ среды выполнения Windows для разработки приложений UWP. Сведения о библиотека шаблонов C++ среды выполнения Windows см. в разделе [библиотеки шаблонов C++ (WRL) среды выполнения Windows](../windows/windows-runtime-cpp-template-library-wrl.md).

## <a name="see-also"></a>См. также

[Visual C++](../visual-cpp-in-visual-studio.md)<br/>
