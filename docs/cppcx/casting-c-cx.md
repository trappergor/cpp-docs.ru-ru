---
title: "Приведение (C + +/ CX) | Документы Microsoft"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
ms.assetid: 5247f6c7-6a0a-4021-97c9-21c868bd9455
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5e16aacdf713d1f9ff2b40532abfd2b5d6316f7a
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="casting-ccx"></a>Приведение (C++/CX)
Четыре различных оператора приведения применяются к типам среды выполнения Windows: [оператор static_cast](../cpp/static-cast-operator.md), [оператор dynamic_cast](../cpp/dynamic-cast-operator.md), **оператор safe_cast**, и [ Оператор reinterpret_cast](../cpp/reinterpret-cast-operator.md). `safe_cast` и `static_cast` вызывают исключение, если преобразование не может быть выполнено; [оператор static_cast](../cpp/static-cast-operator.md) также выполняет проверку типов во время компиляции. `dynamic_cast` возвращает значение `nullptr` , если не удается преобразовать тип. Хотя `reinterpret_cast` возвращает значение, отличное от NULL, оно может быть неверным. По этой причине рекомендуется не использовать `reinterpret_cast` , если нет уверенности, что приведение завершится успешно. Кроме того, мы рекомендуем не использовать C-стиль приведения в C + +/ CX код, поскольку это идентично `reinterpret_cast`.  
  
 Компилятор и среда выполнения также выполняют неявное приведение, например в операциях упаковки, когда тип значения или встроенный тип передаются как аргументы в метод, параметры которого имеют тип `Object^`. Теоретически неявное приведение никогда не должно вызвать исключение во время выполнения; если компилятор не может выполнить неявное преобразование, он вызывает ошибку во время компиляции.  
  
Среда выполнения Windows — это абстракция над COM, использующая вместо исключений коды ошибок HRESULT. Как правило, [Platform::InvalidCastException](../cppcx/platform-invalidcastexception-class.md) указывает на низкоуровневую ошибку E_NOINTERFACE модели COM.  
  
## <a name="staticcast"></a>static_cast  
 `static_cast` проверяется во время компиляции, чтобы определить, есть ли отношения наследования между двумя типами. Приведение вызывает ошибку компилятора, если типы не связаны.  
  
 Применение `static_cast` к классу ссылки также вызывает проверку времени выполнения. Применение `static_cast` к классам ссылок может пройти проверку при компиляции, но все равно приведет к сбою во время выполнения; в этом случае создается исключение `Platform::InvalidCastException` . В общем случае не следует обрабатывать эти исключения, поскольку они почти всегда указывают на ошибки программирования, которые можно устранить на этапах разработки и тестирования.  
  
 Используйте `static_cast` , если в коде явно объявлена связь между двумя, и поэтому вы уверены, что приведение должно работать.  
  
```
    interface class A{};  
    public ref class Class1 sealed : A { };  
...  
    A^ obj = ref new Class1(); // Class1 is an A  
    // You know obj is a Class1. The compiler verifies that this is possible, and in C++/CX a run-time check is also performed.  
    Class1^ c = static_cast<Class1^>(obj);
```  
  
## <a name="safecast"></a>safe_cast  
 `safe_cast` Оператор является ofWindows часть среды выполнения. Он выполняет проверку типов во время выполнения и создает исключение `Platform::InvalidCastException` при невозможности преобразования. Используйте `safe_cast` , когда ошибка времени выполнения указывает на исключительные условия. Основное назначение `safe_cast` — помочь в выявлении ошибок программирования на этапе разработки и тестирования в том месте, где они возникают. Обрабатывать исключения не следует, поскольку необработанное исключение само определяет точку сбоя.  
  
 Используйте safe_cast, если в коде не объявлена связь, но вы уверены, что приведение должно работать.  
  
```  
    // A and B are not related  
    interface class A{};  
    interface class B{};  
    public ref class Class1 sealed : A, B { };  
...  
    A^ obj = ref new Class1();  
  
    // You know that obj’s backing type implements A and B, but  
    // the compiler can’t tell this by comparing A and B. The run-time type check succeeds.  
    B^ obj2 = safe_cast<B^>(obj);  
```  
  
## <a name="dynamiccast"></a>dynamic_cast  
 Используйте `dynamic_cast` при приведении объекта (в частности, hat `^`) к более производному типу, когда предполагается, целевой объект иногда может быть `nullptr` или когда приведение может завершиться ошибкой, и необходимо обработать это условие как обычный код путь, а не исключение. Например, в **пустое приложение (универсальные приложения Windows)** шаблона проекта, `OnLaunched` метод в `app.xamp.cpp` использует `dynamic_cast` для проверки наличия содержимое окна приложения. Не является ошибкой при отсутствии содержимого — это ожидаемое условие. `Windows::Current::Content` является `Windows::UI::XAML::UIElement` , а преобразование выполняется в тип `Windows::UI.XAML::Controls::Frame`, который в иерархии наследования является более производным типом.  
```
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
...  
```  
 Другое использование оператора `dynamic_cast` — проверка объекта `Object^` , чтобы определить, содержит ли он тип упакованного значения. В этом случае вы пытаетесь применить `dynamic_cast<Platform::Box>` или `dynamic_cast<Platform::IBox>`.  
  
 **dynamic_cast и отслеживание ссылок (%)**  
  
 Оператор `dynamic_cast` также можно применять к отслеживаемым ссылкам, но в этом случае приведение ведет себя как `safe_cast`. Оно создает исключение `Platform::InvalidCastException` при сбое, потому что отслеживаемая ссылка не может иметь значение `nullptr`.  
  
## <a name="reinterpretcast"></a>reinterpret_cast  
 Не рекомендуется использовать [reinterpret_cast](../cpp/reinterpret-cast-operator.md) , поскольку проверка не выполняется ни во время компиляции, ни во время выполнения. В худшем случае при использовании `reinterpret_cast` ошибки программирования могут остаться незамеченными во время разработки и вызвать незначительные или катастрофические сбои в поведении программы. Поэтому использовать `reinterpret_cast` рекомендуется только в тех редких случаях, когда необходимо выполнять приведение между несвязанными типами и известно, что такое приведение будет выполнено успешно. Пример такого редкого использования — преобразование aWindows тип среды выполнения к его базовому типу ABI — это означает, что вы будете следить за подсчетом ссылок для объекта. Для этого рекомендуется использовать интеллектуальный указатель [ComPtr Class](../cpp/com-ptr-t-class.md) . В противном случае необходимо явно вызывать Release для интерфейса. В следующем примере показано, как класс ссылки может быть приведен к `IInspectable*`.  
  
```  
#include <wrl.h>  
using namespace Microsoft::WRL;  
auto winRtObject = ref new SomeWinRTType();  
ComPtr<IInspectable> inspectable = reinterpret_cast<IInspectable*>(winRtObject);  
...
```  
  
 Если вы используете `reinterpret_cast` для преобразования из oneWindows интерфейс среды выполнения в другой, вызвать объект освобождается дважды. Поэтому это приведение следует использовать только при преобразовании в интерфейсы, не относящиеся к[!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] .  
  
 **Типы ABI**  
  
-   Типы ABI расположены в заголовках в Windows SDK. Для удобства имена заголовков соответствуют именам пространств имен, например `windows.storage.h`.  
  
-   Типы ABI расположены в специальном пространстве имен ABI, например `ABI::Windows::Storage::Streams::IBuffer*`.  
  
-   Преобразование между типом интерфейса среды выполнения aWindows и его эквивалентным типом ABI всегда безопасно — то есть `IBuffer^` для `ABI::IBuffer*`.  
  
-   Класс среды выполнения AWindows среда выполнения всегда должны быть преобразованы в `IInspectable*` или интерфейс по умолчанию, если последний известен.  
  
-   После преобразования к типам ABI вы управляете временем жизни типа и должны соблюдать правила модели COM. Рекомендуется использовать `WRL::ComPtr` , чтобы упростить управление временем жизни указателей ABI.  
  
 В следующей таблице приведены случаи, в которых безопасно использовать `reinterpret_cast`. В каждом случае приведение безопасно в обоих направлениях.  
  
|||  
|-|-|  
|HSTRING|String^|  
|HSTRING*|String^*|  
|IInspectable*|Object^|  
|IInspectable**|Object^*|  
|IInspectable-derived-type*|same-interface-from-winmd^|  
|IInspectable-derived-type**|same-interface-from-winmd^*|  
|IDefault-interface-of-RuntimeClass*|same-RefClass-from-winmd^|  
|IDefault-interface-of-RuntimeClass**|same-RefClass-from-winmd^*|  
  
## <a name="see-also"></a>См. также  
 [Система типов](../cppcx/type-system-c-cx.md)   
 [Справочник по языку Visual C++](../cppcx/visual-c-language-reference-c-cx.md)   
 [Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)
