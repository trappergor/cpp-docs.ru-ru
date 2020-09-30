---
title: Справочник по языку C++/CX
ms.date: 09/15/2017
ms.assetid: 3f6abf92-4e5e-4ed8-8e11-f9252380d30a
ms.openlocfilehash: f28270ace3965a3cf89e250a873af14e48390708
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91507428"
---
# <a name="ccx-language-reference"></a>Справочник по языку C++/CX

C++/CX — это набор расширений для языка C++, который позволяет создавать приложения Windows и среда выполнения Windows компонентов в идиоме, как можно ближе к современным C++. Используйте C++/CX для написания приложений и компонентов Windows в машинном коде, которые легко взаимодействуют с Visual C#, Visual Basic и JavaScript, а также с другими языками, поддерживающими среда выполнения Windows. В тех редких случаях, когда требуется прямой доступ к необработанным COM-интерфейсам или неисключительный код, можно использовать [библиотеку шаблонов C++ среда выполнения Windows (WRL)](./wrl/windows-runtime-cpp-template-library-wrl.md).

> [!NOTE]
> **/WinRT является рекомендуемой альтернативой C++для/CX. [ C++](/windows/uwp/cpp-and-winrt-apis/index)** Это новая, стандартная проекция языка C++ 17 для среда выполнения Windows API, доступных в новейшем пакете SDK для Windows 10 из версии 1803. C++/WinRT реализован полностью в файлах заголовков и предназначен для предоставления доступа к современным API Windows с помощью первого класса.
>
> С помощью C++/WinRT можно использовать и создавать интерфейсы среда выполнения Windows API, используя любой стандартно совместимый с C++ 17 компилятор. C++/WinRT, как правило, работает лучше и создает меньше двоичных файлов, чем любой другой языковой параметр для среда выполнения Windows. Мы продолжим предоставлять поддержку C++/CX и WRL, но в новых приложениях настоятельно рекомендуется использовать C++/WinRT. См. дополнительные сведения о [C++/WinRT](/windows/uwp/cpp-and-winrt-apis/index).

С помощью C++/CX можно создавать:

- Приложения C++ универсальная платформа Windows (UWP), использующие XAML для определения пользовательского интерфейса и использования собственного стека. Дополнительные сведения см. [в статье Создание приложения "Hello World" в C++ (UWP)](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp).

- Компоненты C++ среда выполнения Windows, которые могут использоваться приложениями Windows на основе JavaScript. Для получения дополнительной информации см. [Creating Windows Runtime Components in C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

- Игры Windows на базе DirectX и приложения, активно использующие графику. Дополнительные сведения см. в статье [Создание простой игры UWP с помощью DirectX](/windows/uwp/gaming/tutorial--create-your-first-uwp-directx-game).

## <a name="related-articles"></a>Похожие статьи

| Ссылка | Описание |
|--|--|
| [Краткий справочник](../cppcx/quick-reference-c-cx.md) | Таблица ключевых слов и операторов для C++/CX. |
| [Система типов](../cppcx/type-system-c-cx.md) | Описывает базовые типы C++/CX и конструкции программирования, а так же использование C++/CX для использования и создания типов среда выполнения Windows. |
| [Сборка приложений и библиотек](../cppcx/building-apps-and-libraries-c-cx.md) | Описывает использование интегрированной среды разработки для создания приложений и ссылки на статические библиотеки и библиотеки DLL. |
| [Взаимодействие с другими языками](../cppcx/interoperating-with-other-languages-c-cx.md) | Описывает, как компоненты, написанные с помощью C++/CX, можно использовать с компонентами, написанными на JavaScript, на любом управляемом языке или в библиотеке шаблонов среда выполнения Windows C++. |
| [Работа с потоками и маршалирование](../cppcx/threading-and-marshaling-c-cx.md) | Принципы указания поведения при использовании потоков и маршалинга в создаваемых компонентах. |
| [Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md) | Справочная документация по следующим пространствам имен: по умолчанию, Platform, Platform::Collections и другим связанным с ними пространствам имен. |
| [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) | Список функций CRT, недоступных для использования в приложениях среды выполнения Windows. |
| [Приступая к работе с приложениями для Windows 10](/windows/uwp/get-started/) | Общие рекомендации по приложениям Windows 10, а также ссылки на дополнительную информацию. |
| [C++/CX часть 0 из \[ n \] : введение](https://devblogs.microsoft.com/cppblog/ccx-part-0-of-n-an-introduction/)<br /><br />[C++/CX, часть 1 из \[ n \] : простой класс](https://devblogs.microsoft.com/cppblog/ccx-part-1-of-n-a-simple-class/)<br /><br />[C++/CX, часть 2 из \[ n \] : типы, которые выизносют шляпы](https://devblogs.microsoft.com/cppblog/ccx-part-2-of-n-types-that-wear-hats/)<br /><br />[C++/CX, часть 3 из \[ n \] : в конструкции](https://devblogs.microsoft.com/cppblog/ccx-part-3-of-n-under-construction/)<br /><br />[C++/CX, часть 4 из \[ n \] : статические функции членов](https://devblogs.microsoft.com/cppblog/ccx-part-4-of-n-static-member-functions/)| Вводный ряд блогов по C++/CX. |
