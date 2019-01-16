---
title: Как выполнить Активация и использование компонента среды выполнения Windows, с использованием WRL
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 54828f02-6af3-45d1-b965-d0104442f8d5
ms.openlocfilehash: 4b8ce40e6c28f952596cab48848873be91b73c95
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336519"
---
# <a name="how-to-activate-and-use-a-windows-runtime-component-using-wrl"></a>Как выполнить Активация и использование компонента среды выполнения Windows, с использованием WRL

В этом документе показано, как использовать Windows шаблонов среды выполнения C++ Library (WRL) для инициализации среды выполнения Windows и как активация и использование компонента среды выполнения Windows.

Для использования компонента необходимо получить указатель интерфейса на тип, который реализуется компонентом. И поскольку лежащие в основе среды выполнения Windows является компонентом модели объектов (COM), необходимо соблюдать правила модели COM для поддержки экземпляра типа. Например, необходимо поддерживать *счетчика ссылок* , определяющий, когда тип удаляется из памяти.

Чтобы упростить использование среды выполнения Windows, библиотека шаблонов C++ среды выполнения Windows предоставляет шаблон интеллектуального указателя, [ComPtr\<T >](comptr-class.md), который автоматически выполняет подсчет ссылок. При объявлении переменной укажите `ComPtr<` *имя интерфейса* `>` *идентификатор*. Для обращения к членам интерфейса примените оператор доступа к членам класса в виде стрелки (`->`) к идентификатору.

> [!IMPORTANT]
> При вызове функции интерфейса, всегда проверяйте возвращаемое значение HRESULT.

## <a name="activating-and-using-a-windows-runtime-component"></a>Активация и использование компонента среды выполнения Windows

В следующих действиях используется `Windows::Foundation::IUriRuntimeClass` интерфейс, чтобы продемонстрировать, как создать фабрику активации для компонента среды выполнения Windows, создания экземпляра этого компонента и получать значение свойства. Также вы узнаете, каким образом выполняется инициализация среды выполнения Windows. Полный пример выглядит следующим образом.

> [!IMPORTANT]
> Несмотря на то, что обычно используется библиотека шаблонов C++ среды выполнения Windows в приложении универсальной платформы Windows (UWP), в этом примере используется консольное приложение для иллюстрации. Функции, такие как `wprintf_s` не доступны из приложения UWP. Дополнительные сведения о типах и функциях, которые можно использовать в приложении UWP, см. в разделе [функции CRT не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) и [Win32 и COM для приложений UWP](/uwp/win32-and-com/win32-and-com-for-uwp-apps).

#### <a name="to-activate-and-use-a-windows-runtime-component"></a>Активация и использование компонента среды выполнения Windows

1. Включить (`#include`) все необходимые заголовки стандартной библиотеки C++, библиотека шаблонов C++ среды выполнения Windows или среды выполнения Windows.

   [!code-cpp[wrl-consume-component#2](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_1.cpp)]

   Рекомендуется использовать директиву `using namespace` в CPP-файле, чтобы сделать код более удобочитаемым.

2. Инициализируйте поток, в котором выполняется приложение. Каждое приложение должно инициализировать свой поток и потоковую модель. В этом примере используется [Microsoft::WRL::Wrappers::RoInitializeWrapper](roinitializewrapper-class.md) класса для инициализации среды выполнения Windows и указывает [RO_INIT_MULTITHREADED](https://msdn.microsoft.com/library/windows/apps/br224661.aspx) качестве потоковой модели. Класс `RoInitializeWrapper` вызывает `Windows::Foundation::Initialize` при создании и `Windows::Foundation::Uninitialize` при удалении.

   [!code-cpp[wrl-consume-component#3](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_2.cpp)]

   Во втором операторе [RoInitializeWrapper::HRESULT](roinitializewrapper-class.md#hresult) оператор возвращает `HRESULT` из вызова `Windows::Foundation::Initialize`.

3. Создание *фабрику активации* для `ABI::Windows::Foundation::IUriRuntimeClassFactory` интерфейс.

   [!code-cpp[wrl-consume-component#4](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_3.cpp)]

   Среда выполнения Windows использует полные имена для идентификации типов. `RuntimeClass_Windows_Foundation_Uri` Параметр представляет собой строку, которая предоставляется средой выполнения Windows и содержит имя класса необходимая среда выполнения.

4. Инициализировать [Microsoft::WRL::Wrappers::HString](hstring-class.md) переменной, представляющей URI `"http://www.microsoft.com"`.

   [!code-cpp[wrl-consume-component#6](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_4.cpp)]

   В среде выполнения Windows нет необходимости выделять память для строки, который будет использоваться среда выполнения Windows. Вместо этого среда выполнения Windows создает копию строки в буфере, который поддерживает и использует для выполнения операций и затем возвращает дескриптор буфера он создан.

5. Используйте метод фабрики `IUriRuntimeClassFactory::CreateUri` для создания объекта `ABI::Windows::Foundation::IUriRuntimeClass`.

   [!code-cpp[wrl-consume-component#7](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_5.cpp)]

6. Вызовите метод `IUriRuntimeClass::get_Domain` для получения значения свойства `Domain`.

   [!code-cpp[wrl-consume-component#8](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_6.cpp)]

7. Выведите доменное имя с символом перевода строки в окно консоли. Все объекты `ComPtr` и RAII покидают область действия и автоматически освобождаются.

   [!code-cpp[wrl-consume-component#9](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_7.cpp)]

   [WindowsGetStringRawBuffer](https://msdn.microsoft.com/library/windows/apps/br224636.aspx) функция получает базовый формат Юникода строки URI.

Ниже приведен полный пример.

[!code-cpp[wrl-consume-component#1](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_8.cpp)]

## <a name="compiling-the-code"></a>Компиляция кода

Чтобы скомпилировать код, скопируйте его и затем вставьте его в проект Visual Studio или вставьте его в файл с именем `wrl-consume-component.cpp` и выполните следующую команду в окне командной строки Visual Studio.

`cl.exe wrl-consume-component.cpp runtimeobject.lib`

## <a name="see-also"></a>См. также

[Библиотека шаблонов C++ среды выполнения Windows (WRL)](windows-runtime-cpp-template-library-wrl.md)