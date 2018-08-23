---
title: Справочник по языку C++ (C + +/ CX) | Документация Майкрософт
ms.custom: ''
ms.date: 09/15/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 3f6abf92-4e5e-4ed8-8e11-f9252380d30a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 801a88573133a68beec4855dc499fcba27bb64e8
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42593873"
---
# <a name="visual-c-language-reference-ccx"></a>Справочник по языку C++ (C++/CX)

C + +/ CX представляет собой набор расширений языка C++, которые позволяют создавать приложения Windows и компонентов среды выполнения Windows с идиоматикой, близкой к современному максимально C++. Использовать C + +/ CX для написания приложений Windows и компонентов в машинном коде, легко взаимодействующих с Visual C#, Visual Basic и JavaScript и другими языками, поддерживающими среды выполнения Windows. В редких случаях, когда требуется прямой доступ к интерфейсам COM или код без поддержки исключений, можно использовать [библиотеки шаблонов C++ (WRL) среды выполнения Windows](../windows/windows-runtime-cpp-template-library-wrl.md).

> [!NOTE]
> C + +/ WinRT — это новый "," стандартный C ++ 17 языковых проекции для API среды выполнения Windows. Она доступна в последний пакет SDK Windows 10 версии 1803 и далее. C + +/ WinRT реализуется полностью в файлах заголовков и предоставляющая с первоклассный доступ к современных API Windows.

> С использованием C + +/ WinRT, можно одновременно использовать и создавать интерфейсы API среды выполнения Windows, с помощью любой совместимый со стандартами C ++ 17 компилятор. C + +/ WinRT обычно работает быстрее и создает меньше двоичных файлов, чем любой другой параметр языка для среды выполнения Windows. Мы продолжим предоставлять поддержку C + +/ CX и WRL, но настоятельно рекомендуется, использовать новые приложения C + +/ WinRT. Дополнительные сведения см. в разделе [C + +/ WinRT](https://docs.microsoft.com/windows/uwp/cpp-and-winrt-apis/index).


С помощью C + +/ CX, можно создать:

- Приложения C++ универсальной платформы Windows (UWP), использующие XAML для определения пользователя интерфейса и используется собственный стек. Дополнительные сведения см. в разделе [Создание приложения «hello world» в C++ (UWP)](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp).

- Компоненты среды выполнения Windows на C++, которые можно использовать их в приложениях Windows на базе JavaScript. Дополнительные сведения см. в разделе [создание компонентов среды выполнения Windows в C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

- Игры Windows на базе DirectX и приложения, активно использующие графику. Дополнительные сведения см. в разделе [создание простой игрой UWP с помощью DirectX](/windows/uwp/gaming/tutorial--create-your-first-metro-style-directx-game).

## <a name="related-articles"></a>Связанные статьи

|||
|-|-|
|[Краткий справочник](../cppcx/quick-reference-c-cx.md)|Таблица ключевых слов и операторов C + +/ CX.|
|[Система типов](../cppcx/type-system-c-cx.md)|Описывает основные C + +/ CX типов и конструкций программирования и как использовать C + +/ CX и создания типов среды выполнения Windows.|
|[Создание приложений и библиотек](../cppcx/building-apps-and-libraries-c-cx.md)|Принципы использования интегрированной среды разработки для построения приложений и подключения статических библиотек и DLL.|
|[Взаимодействие с другими языками](../cppcx/interoperating-with-other-languages-c-cx.md)|Рассматриваются как компоненты, написанные с использованием C + +/ CX можно использовать с компонентами, написанными на языке JavaScript, все управляемые язык или библиотека шаблонов C++ среды выполнения Windows.|
|[Работа с потоками и маршалинг](../cppcx/threading-and-marshaling-c-cx.md)|Принципы указания поведения при использовании потоков и маршалинга в создаваемых компонентах.|
|[Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)|Справочная документация по следующим пространствам имен: по умолчанию, Platform, Platform::Collections и другим связанным с ними пространствам имен.|
|[Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)|Список функций CRT, недоступных для использования в приложениях среды выполнения Windows.|
|[Практические руководства по приложениям Windows 10](http://msdn.microsoft.com/library/windows/apps/xaml/mt244352.aspx)|Общие рекомендации по приложениям Windows 10, а также ссылки на дополнительную информацию.|
|[C + +/ CX: часть 0 из \[n\]: введение](https://blogs.msdn.microsoft.com/vcblog/2012/08/29/ccx-part-0-of-n-an-introduction/)<br /><br />[C + +/ CX: часть 1 из \[n\]: простой класс](https://blogs.msdn.microsoft.com/vcblog/2012/09/05/ccx-part-1-of-n-a-simple-class/)<br /><br />[C + +/ CX: часть 2 из \[n\]: типы крышками](https://blogs.msdn.microsoft.com/vcblog/2012/09/17/ccx-part-2-of-n-types-that-wear-hats/)<br /><br />[C + +/ CX: часть 3 из \[n\]: В процессе построения](https://blogs.msdn.microsoft.com/vcblog/2012/10/05/ccx-part-3-of-n-under-construction/)<br /><br />[C + +/ CX: часть 4 из \[n\]: статические функции-члены](https://blogs.msdn.microsoft.com/vcblog/2012/10/19/ccx-part-4-of-n-static-member-functions/)|Вводные серии публикаций в блоге Visual C++, C + +/ CX.|
