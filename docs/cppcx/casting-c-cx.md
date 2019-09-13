---
title: Приведение (C++/CX)
ms.date: 06/19/2018
ms.assetid: 5247f6c7-6a0a-4021-97c9-21c868bd9455
ms.openlocfilehash: 6711320fd9ca52360f702e029fdc8e129c90c6cd
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740541"
---
# <a name="casting-ccx"></a>Приведение (C++/CX)

К среда выполнения Windows типам применяются четыре различных оператора приведения: [оператор static_cast](../cpp/static-cast-operator.md), [оператор dynamic_cast](../cpp/dynamic-cast-operator.md), **оператор safe_cast**и [оператор reinterpret_cast](../cpp/reinterpret-cast-operator.md). **safe_cast** и **static_cast** создают исключение, если преобразование не может быть выполнено; [оператор static_cast](../cpp/static-cast-operator.md) также выполняет проверку типов во время компиляции. **dynamic_cast** возвращает **nullptr** , если не удается преобразовать тип. Несмотря на то, что **reinterpret_cast** возвращает значение, отличное от NULL, оно может быть недопустимым. По этой причине не рекомендуется использовать **reinterpret_cast** , если не известно, что приведение будет выполняться неверно. Кроме того, не рекомендуется использовать приведения в стиле C в коде C++/CX, так как они идентичны **reinterpret_cast**.

Компилятор и среда выполнения также выполняют неявное приведение, например в операциях упаковки, когда тип значения или встроенный тип передаются как аргументы в метод, параметры которого имеют тип `Object^`. Теоретически неявное приведение никогда не должно вызвать исключение во время выполнения; если компилятор не может выполнить неявное преобразование, он вызывает ошибку во время компиляции.

Среда выполнения Windows является абстракцией по сравнению с COM, в которой вместо исключений используются коды ошибок HRESULT. Как правило, [Platform::InvalidCastException](../cppcx/platform-invalidcastexception-class.md) указывает на низкоуровневую ошибку E_NOINTERFACE модели COM.

## <a name="static_cast"></a>static_cast

Значение **static_cast** проверяется во время компиляции, чтобы определить, существует ли отношение наследования между двумя типами. Приведение вызывает ошибку компилятора, если типы не связаны.

**Static_cast** в классе ссылки также приводит к выполнению проверки во время выполнения. **Static_cast** в классе ссылки может передавать проверку времени компиляции, но по-прежнему завершается сбоем во время выполнения. в этом случае `Platform::InvalidCastException` создается исключение. В общем случае не следует обрабатывать эти исключения, поскольку они почти всегда указывают на ошибки программирования, которые можно устранить на этапах разработки и тестирования.

Используйте **static_cast** , если в коде явным образом объявляется связь между двумя типами, и поэтому убедитесь, что приведение должно работать.

```cpp
    interface class A{};
    public ref class Class1 sealed : A { };
    // ...
    A^ obj = ref new Class1(); // Class1 is an A
    // You know obj is a Class1. The compiler verifies that this is possible, and in C++/CX a run-time check is also performed.
    Class1^ c = static_cast<Class1^>(obj);
```

## <a name="safe_cast"></a>safe_cast

Оператор **safe_cast** является частью среда выполнения Windows. Он выполняет проверку типов во время выполнения и создает исключение `Platform::InvalidCastException` при невозможности преобразования. Используйте **safe_cast** , если ошибка времени выполнения указывает на исключительную ситуацию. Основное назначение **safe_cast** — помочь определить ошибки программирования во время этапов разработки и тестирования в момент возникновения. Обрабатывать исключения не следует, поскольку необработанное исключение само определяет точку сбоя.

Используйте safe_cast, если в коде не объявлена связь, но вы уверены, что приведение должно работать.

```cpp
    // A and B are not related
    interface class A{};
    interface class B{};
    public ref class Class1 sealed : A, B { };
    // ...
    A^ obj = ref new Class1();

    // You know that obj’s backing type implements A and B, but
    // the compiler can’t tell this by comparing A and B. The run-time type check succeeds.
    B^ obj2 = safe_cast<B^>(obj);
```

## <a name="dynamic_cast"></a>dynamic_cast

Функция **dynamic_cast** используется при приведении объекта (точнее, a Hat **^** ) к более производному типу, предполагается, что целевой объект может быть в **nullptr** , а приведение может завершиться ошибкой, и вы хотите обрабатывать это условие как обычный путь кода вместо исключения. Например, в шаблоне `OnLaunched` проекта **пустого приложения (универсальное приложение Windows)** метод в App. ксамп. cpp использует **dynamic_cast** для проверки наличия содержимого в окне приложения. Не является ошибкой при отсутствии содержимого — это ожидаемое условие. `Windows::Current::Content` является `Windows::UI::XAML::UIElement` , а преобразование выполняется в тип `Windows::UI.XAML::Controls::Frame`, который в иерархии наследования является более производным типом.

```cpp
void App::OnLaunched(Windows::ApplicationModel::Activation::LaunchActivatedEventArgs^ args)
{
    auto rootFrame = dynamic_cast<Frame^>(Window::Current->Content);

    // Do not repeat app initialization when the window already has content,
    // just ensure that the window is active
    if (rootFrame == nullptr)
    {
        // Create a Frame to act as the navigation context and associate it with
        // a SuspensionManager key
        rootFrame = ref new Frame();
        // ...
    }
}
```

Другим применением **dynamic_cast** является проверка объекта `Object^` , чтобы определить, содержит ли он упакованный тип значения. В этом случае вы пытаетесь применить `dynamic_cast<Platform::Box>` или `dynamic_cast<Platform::IBox>`.

## <a name="dynamic_cast-and-tracking-references-"></a>dynamic_cast и отслеживание ссылок (%)

Можно также применить **dynamic_cast** к отслеживаемой ссылке, но в этом случае приведение ведет себя как **safe_cast**. Он вызывается `Platform::InvalidCastException` при сбое, так как Отслеживаемая ссылка не может иметь значение **nullptr**.

## <a name="reinterpret_cast"></a>reinterpret_cast

Не рекомендуется использовать [reinterpret_cast](../cpp/reinterpret-cast-operator.md) , поскольку проверка не выполняется ни во время компиляции, ни во время выполнения. В худшем случае **reinterpret_cast** позволяет ошибкам программирования обнаруживать незамеченные во время разработки и вызывать серьезные или разрушительные ошибки в поведении программы. Поэтому рекомендуется использовать **reinterpret_cast** только в редких случаях, когда необходимо выполнить приведение между несвязанными типами и известно, что приведение будет завершено. Примером редкого использования является преобразование типа среда выполнения Windows в его базовый тип ABI — это означает, что вы контролируете подсчет ссылок для объекта. Для этого рекомендуется использовать интеллектуальный указатель [ComPtr Class](../cpp/com-ptr-t-class.md) . В противном случае необходимо явно вызывать Release для интерфейса. В следующем примере показано, как класс ссылки может быть приведен к `IInspectable*`.

```cpp
#include <wrl.h>
using namespace Microsoft::WRL;
auto winRtObject = ref new SomeWinRTType();
ComPtr<IInspectable> inspectable = reinterpret_cast<IInspectable*>(winRtObject);
// ...
```

Если вы используете **reinterpret_cast** для преобразования из интерфейса среды выполнения оневиндовс в другой, объект будет освобожден дважды. Поэтому используйте это приведение только при преобразовании в интерфейс расширений, неC++ относящихся к компоненту.

## <a name="abi-types"></a>Типы ABI

- Типы ABI расположены в заголовках в Windows SDK. Для удобства имена заголовков соответствуют именам пространств имен, например `windows.storage.h`.

- Типы ABI расположены в специальном пространстве имен ABI, например `ABI::Windows::Storage::Streams::IBuffer*`.

- Преобразования между типом интерфейса Среда выполнения Windows и его эквивалентным типом ABI всегда являются надежными, то есть `IBuffer^` с `ABI::IBuffer*`.

- Класс среды выполнения среда выполнения Windows всегда должен быть преобразован в `IInspectable*` или в его интерфейс по умолчанию, если он известен.

- После преобразования к типам ABI вы управляете временем жизни типа и должны соблюдать правила модели COM. Рекомендуется использовать `WRL::ComPtr` , чтобы упростить управление временем жизни указателей ABI.

В следующей таблице перечислены случаи, в которых можно использовать **reinterpret_cast**в качестве безопасного. В каждом случае приведение безопасно в обоих направлениях.

|||
|-|-|
|`HSTRING`|`String^`|
|`HSTRING*`|`String^*`|
|`IInspectable*`|`Object^`|
|`IInspectable**`|`Object^*`|
|`IInspectable-derived-type*`|`same-interface-from-winmd^`|
|`IInspectable-derived-type**`|`same-interface-from-winmd^*`|
|`IDefault-interface-of-RuntimeClass*`|`same-RefClass-from-winmd^`|
|`IDefault-interface-of-RuntimeClass**`|`same-RefClass-from-winmd^*`|

## <a name="see-also"></a>См. также

- [Система типов](../cppcx/type-system-c-cx.md)
- [Справочник по языку C++/CX](../cppcx/visual-c-language-reference-c-cx.md)
- [Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)
