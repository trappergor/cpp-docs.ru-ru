---
title: C++Справочник по языку/CX
ms.date: 09/15/2017
ms.assetid: 3f6abf92-4e5e-4ed8-8e11-f9252380d30a
ms.openlocfilehash: ed8e2374daf862e99517fb113e869504b7c7aabc
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740869"
---
# <a name="ccx-language-reference"></a>C++Справочник по языку/CX

C++/CX — это набор расширений для C++ языка, позволяющих создавать приложения Windows и среда выполнения Windows компоненты в идиоме, как можно ближе к современным. C++ Используйте C++код/CX для написания приложений и компонентов Windows в машинном коде, которые легко C#взаимодействуют с визуальными элементами, Visual Basic и JavaScript, а также с другими языками, поддерживающими среда выполнения Windows. В тех редких случаях, когда требуется прямой доступ к необработанным COM-интерфейсам или неисключительный код, можно использовать [библиотеку шаблонов среда выполнения Windows C++ (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md).

> [!NOTE]
> **/WinRT является рекомендуемой альтернативой C++для/CX. [ C++](/windows/uwp/cpp-and-winrt-apis/index) Это новая, стандартная проекция языка C++ 17 для среда выполнения Windows API, доступных в новейшем пакете SDK для Windows 10 из версии 1803. C++/WinRT реализован полностью в файлах заголовков и предназначен для предоставления доступа к современным API Windows с помощью первого класса.
>
> С C++помощью/WinRT можно использовать и создавать интерфейсы Среда выполнения Windows API, используя любой стандартно совместимый с c++ 17 компилятор. C++/WinRT обычно работает лучше и создает меньше двоичных файлов, чем любой другой языковой параметр для среда выполнения Windows. Мы продолжим предоставлять поддержку C++/CX и WRL, но в новых приложениях настоятельно рекомендуется использовать C++/WinRT. См. дополнительные сведения о [C++/WinRT](/windows/uwp/cpp-and-winrt-apis/index).

С помощью C++/CX можно создать:

- C++Приложения универсальная платформа Windows (UWP), использующие XAML для определения пользовательского интерфейса и использования собственного стека. Дополнительные сведения см. [в статье Создание приложения "Hello World" в C++ (UWP)](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp).

- C++Среда выполнения Windows компоненты, которые могут использоваться приложениями Windows на основе JavaScript. Для получения дополнительной информации см. [Creating Windows Runtime Components in C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

- Игры Windows на базе DirectX и приложения, активно использующие графику. Дополнительные сведения см. в статье [Создание простой игры UWP с помощью DirectX](/windows/uwp/gaming/tutorial--create-your-first-uwp-directx-game).

## <a name="related-articles"></a>Связанные статьи

|||
|-|-|
|[Краткий справочник](../cppcx/quick-reference-c-cx.md)|Таблица ключевых слов и операторов для C++/CX.|
|[Система типов](../cppcx/type-system-c-cx.md)|Описывает основные C++типы и конструкции программирования/CX, а так же использование кода C++/CX для использования и создания типов Среда выполнения Windows.|
|[Построение приложений и библиотек](../cppcx/building-apps-and-libraries-c-cx.md)|Описывает использование интегрированной среды разработки для создания приложений и ссылки на статические библиотеки и библиотеки DLL.|
|[Взаимодействие с другими языками](../cppcx/interoperating-with-other-languages-c-cx.md)|Описывает, как компоненты, написанные с помощью C++кода/CX, можно использовать с компонентами, написанными на JavaScript, на любом управляемом языке или C++ в библиотеке шаблонов среда выполнения Windows.|
|[Работа с потоками и маршалинг](../cppcx/threading-and-marshaling-c-cx.md)|Принципы указания поведения при использовании потоков и маршалинга в создаваемых компонентах.|
|[Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)|Справочная документация по следующим пространствам имен: по умолчанию, Platform, Platform::Collections и другим связанным с ними пространствам имен.|
|[Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)|Список функций CRT, недоступных для использования в приложениях среды выполнения Windows.|
|[Начало работы с приложениями Windows 10](/windows/uwp/get-started/)|Общие рекомендации по приложениям Windows 10, а также ссылки на дополнительную информацию.|
|[C++/CX, часть 0 \[из\]n: Введение](https://blogs.msdn.microsoft.com/vcblog/2012/08/29/ccx-part-0-of-n-an-introduction/)<br /><br />[C++/CX, часть 1 \[из\]n: Простой класс](https://blogs.msdn.microsoft.com/vcblog/2012/09/05/ccx-part-1-of-n-a-simple-class/)<br /><br />[C++/CX, часть 2 \[из\]n: Типы, которые являются недействительной шляпой](https://blogs.msdn.microsoft.com/vcblog/2012/09/17/ccx-part-2-of-n-types-that-wear-hats/)<br /><br />[C++/CX, часть 3 \[из\]n: В процессе создания](https://blogs.msdn.microsoft.com/vcblog/2012/10/05/ccx-part-3-of-n-under-construction/)<br /><br />[C++/CX, часть 4 \[из\]n: Статические функции членов](https://blogs.msdn.microsoft.com/vcblog/2012/10/19/ccx-part-4-of-n-static-member-functions/)|Вводный ряд блогов C++по/CX.|
