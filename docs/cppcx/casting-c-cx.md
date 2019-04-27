---
title: Приведение (C++/CX)
ms.date: 06/19/2018
ms.assetid: 5247f6c7-6a0a-4021-97c9-21c868bd9455
ms.openlocfilehash: 65d489d14c91b462e5a2bbe8bd60fce2657904a7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62258217"
---
# <a name="casting-ccx"></a>Приведение (C++/CX)

Четыре различных оператора приведения применяются к типам среды выполнения Windows: [оператор static_cast](../cpp/static-cast-operator.md), [оператор dynamic_cast](../cpp/dynamic-cast-operator.md), **оператор safe_cast**, и [ Оператор reinterpret_cast](../cpp/reinterpret-cast-operator.md). **safe_cast** и **static_cast** вызова исключения, когда не удается выполнить преобразование; [оператор static_cast](../cpp/static-cast-operator.md) также выполняет проверку типов во время компиляции. **dynamic_cast** возвращает **nullptr** Если не удается преобразовать тип. Несмотря на то что **reinterpret_cast** возвращает ненулевое значение, оно может быть неверным. По этой причине мы рекомендуем не использовать **reinterpret_cast** Если известно, что приведение завершится успешно. Кроме того, мы рекомендуем не использовать приведение в стиле C в вашей C++/CX кода, потому что они идентичны **reinterpret_cast**.

Компилятор и среда выполнения также выполняют неявное приведение, например в операциях упаковки, когда тип значения или встроенный тип передаются как аргументы в метод, параметры которого имеют тип `Object^`. Теоретически неявное приведение никогда не должно вызвать исключение во время выполнения; если компилятор не может выполнить неявное преобразование, он вызывает ошибку во время компиляции.

Среда выполнения Windows — это абстракция над COM, использующая вместо исключений коды ошибок HRESULT. Как правило, [Platform::InvalidCastException](../cppcx/platform-invalidcastexception-class.md) указывает на низкоуровневую ошибку E_NOINTERFACE модели COM.

## <a name="staticcast"></a>static_cast

Объект **static_cast** проверяется во время компиляции, чтобы определить, есть ли отношения наследования между двумя типами. Приведение вызывает ошибку компилятора, если типы не связаны.

Объект **static_cast** на ref класс также вызывает проверку времени выполнения для выполнения. Объект **static_cast** на ref можно пройти проверку при компиляции класса, но по-прежнему ошибкой во время выполнения; в данном случае `Platform::InvalidCastException` возникает исключение. В общем случае не следует обрабатывать эти исключения, поскольку они почти всегда указывают на ошибки программирования, которые можно устранить на этапах разработки и тестирования.

Используйте **static_cast** Если код явно объявлена связь между двумя типами, и поэтому известно, что приведение должно работать.

```cpp
    interface class A{};
    public ref class Class1 sealed : A { };
    // ...
    A^ obj = ref new Class1(); // Class1 is an A
    // You know obj is a Class1. The compiler verifies that this is possible, and in C++/CX a run-time check is also performed.
    Class1^ c = static_cast<Class1^>(obj);
```

## <a name="safecast"></a>safe_cast

**Safe_cast** оператор является частью среды выполнения Windows. Он выполняет проверку типов во время выполнения и создает исключение `Platform::InvalidCastException` при невозможности преобразования. Используйте **safe_cast** при сбое выполнения указывает на исключительные условия. Основная цель **safe_cast** призвана помочь в выявлении ошибок программирования во время разработки и тестирования в точке, где они возникают. Обрабатывать исключения не следует, поскольку необработанное исключение само определяет точку сбоя.

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

## <a name="dynamiccast"></a>dynamic_cast

Используйте **dynamic_cast** при приведении объекта (в частности, hat **^**) к более производному типу, когда предполагается, что целевой объект иногда может быть **nullptr** или приведение может завершиться ошибкой, и вы хотите обработать это условие как крышки вместо исключения. Например, в **пустое приложение (универсальные Windows)** шаблона проекта, `OnLaunched` метод в использует app.xamp.cpp **dynamic_cast** для тестирования ли окно приложения имеет содержимое. Не является ошибкой при отсутствии содержимого — это ожидаемое условие. `Windows::Current::Content` является `Windows::UI::XAML::UIElement` , а преобразование выполняется в тип `Windows::UI.XAML::Controls::Frame`, который в иерархии наследования является более производным типом.

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

Другим использованием **dynamic_cast** — проверка `Object^` для определения того, содержит ли он тип упакованного значения. В этом случае вы пытаетесь применить `dynamic_cast<Platform::Box>` или `dynamic_cast<Platform::IBox>`.

## <a name="dynamiccast-and-tracking-references-"></a>dynamic_cast и отслеживание ссылок (%)

Можно также применить **dynamic_cast** отслеживаемой ссылки, но в данном случае приведение ведет себя как **safe_cast**. Он выдает `Platform::InvalidCastException` при сбое, так как отслеживаемая ссылка не может иметь значение **nullptr**.

## <a name="reinterpretcast"></a>reinterpret_cast

Не рекомендуется использовать [reinterpret_cast](../cpp/reinterpret-cast-operator.md) , поскольку проверка не выполняется ни во время компиляции, ни во время выполнения. В худшем случае **reinterpret_cast** делает возможным ошибки незамеченными во время разработки и вызвать незначительные или катастрофические сбои в поведении программы программирования. Таким образом, мы рекомендуем использовать **reinterpret_cast** только в тех редких случаях, когда необходимо выполнять приведение между несвязанными типами и известно, что приведение завершится успешно. Пример такого редкого использования — для преобразования типа среды выполнения Windows к его базовому типу ABI — это означает, что вы будете следить за подсчетом ссылок для объекта. Для этого рекомендуется использовать интеллектуальный указатель [ComPtr Class](../cpp/com-ptr-t-class.md) . В противном случае необходимо явно вызывать Release для интерфейса. В следующем примере показано, как класс ссылки может быть приведен к `IInspectable*`.

```cpp
#include <wrl.h>
using namespace Microsoft::WRL;
auto winRtObject = ref new SomeWinRTType();
ComPtr<IInspectable> inspectable = reinterpret_cast<IInspectable*>(winRtObject);
// ...
```

Если вы используете **reinterpret_cast** преобразование oneWindows интерфейс среды выполнения в другой, можно привести объект освобождается дважды. Таким образом используйте только это приведение при преобразовании к интерфейсу компонента расширения не Visual C++.

## <a name="abi-types"></a>Типы ABI

- Типы ABI расположены в заголовках в Windows SDK. Для удобства имена заголовков соответствуют именам пространств имен, например `windows.storage.h`.

- Типы ABI расположены в специальном пространстве имен ABI, например `ABI::Windows::Storage::Streams::IBuffer*`.

- Преобразования между типом среды выполнения Windows интерфейс и его эквивалентным типом ABI всегда безопасно — то есть `IBuffer^` для `ABI::IBuffer*`.

- Класс среды выполнения среды выполнения Windows всегда должны быть преобразованы в `IInspectable*` или интерфейс по умолчанию, если последний известен.

- После преобразования к типам ABI вы управляете временем жизни типа и должны соблюдать правила модели COM. Рекомендуется использовать `WRL::ComPtr` , чтобы упростить управление временем жизни указателей ABI.

В следующей таблице приведены случаи, в которых можно безопасно использовать **reinterpret_cast**. В каждом случае приведение безопасно в обоих направлениях.

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
- [Справочник по языку Visual C++](../cppcx/visual-c-language-reference-c-cx.md)
- [Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)
