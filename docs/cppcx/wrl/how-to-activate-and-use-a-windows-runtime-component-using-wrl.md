---
title: Практическое руководство. Активация и использование компонента среда выполнения Windows с помощью WRL
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 54828f02-6af3-45d1-b965-d0104442f8d5
ms.openlocfilehash: 59a031968933ab151dc97a8089aff629026f5ea5
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70926063"
---
# <a name="how-to-activate-and-use-a-windows-runtime-component-using-wrl"></a>Практическое руководство. Активация и использование компонента среда выполнения Windows с помощью WRL

В этом документе показано, как использовать библиотеку C++ шаблонов среда выполнения Windows (WRL) для инициализации среда выполнения Windows и активации и использования компонента Среда выполнения Windows.

Для использования компонента необходимо получить указатель интерфейса на тип, который реализуется компонентом. А так как базовая технология среда выполнения Windows является моделью COM, необходимо следовать правилам COM для обслуживания экземпляра типа. Например, необходимо поддерживать *счетчик ссылок* , который определяет, когда тип удаляется из памяти.

Чтобы упростить использование среда выполнения Windows, среда выполнения Windows C++ библиотека шаблонов предоставляет шаблон смарт-указателя [ComPtr\<T >](comptr-class.md), который автоматически выполняет подсчет ссылок. При `ComPtr<`объявлении переменной укажите *идентификатор* *интерфейса-Name* `>` . Для обращения к членам интерфейса примените оператор доступа к членам класса в виде стрелки (`->`) к идентификатору.

> [!IMPORTANT]
> При вызове функции интерфейса всегда проверяйте возвращаемое значение HRESULT.

## <a name="activating-and-using-a-windows-runtime-component"></a>Активация и использование компонента среды выполнения Windows

В следующих шагах используется `Windows::Foundation::IUriRuntimeClass` интерфейс, чтобы продемонстрировать, как создать фабрику активации для Среда выполнения Windows компонента, создать экземпляр этого компонента и получить значение свойства. В них также показано, как инициализировать среда выполнения Windows. Полный пример приведен ниже.

> [!IMPORTANT]
> Хотя обычно библиотека шаблонов среда выполнения Windows C++ используется в приложении универсальная платформа Windows (UWP), в этом примере для иллюстрации используется консольное приложение. Такие функции, `wprintf_s` как, недоступны в приложении UWP. Дополнительные сведения о типах и функциях, которые можно использовать в приложении UWP, см. в разделе [функции CRT, которые не поддерживаются в приложениях универсальная платформа Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) и [Win32 и com для приложений UWP](/uwp/win32-and-com/win32-and-com-for-uwp-apps).

#### <a name="to-activate-and-use-a-windows-runtime-component"></a>Активация и использование компонента среды выполнения Windows

1. Включить (`#include`) все необходимые среда выполнения Windows, библиотеку C++ шаблонов среда выполнения Windows или C++ заголовки стандартной библиотеки.

   [!code-cpp[wrl-consume-component#2](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_1.cpp)]

   Рекомендуется использовать директиву `using namespace` в CPP-файле, чтобы сделать код более удобочитаемым.

2. Инициализируйте поток, в котором выполняется приложение. Каждое приложение должно инициализировать свой поток и потоковую модель. В этом примере используется класс [Microsoft:: WRL:: оболочки:: RoInitializeWrapper](roinitializewrapper-class.md) для инициализации среда выполнения Windows и указывается [RO_INIT_MULTITHREADED](/windows/win32/api/roapi/ne-roapi-ro_init_type) в качестве потоковой модели. Класс `RoInitializeWrapper` вызывает `Windows::Foundation::Initialize` при создании и `Windows::Foundation::Uninitialize` при удалении.

   [!code-cpp[wrl-consume-component#3](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_2.cpp)]

   Во второй инструкции оператор [RoInitializeWrapper:: HRESULT](roinitializewrapper-class.md#hresult) возвращает `HRESULT` `Windows::Foundation::Initialize`из вызова.

3. Создайте *фабрику активации* для `ABI::Windows::Foundation::IUriRuntimeClassFactory` интерфейса.

   [!code-cpp[wrl-consume-component#4](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_3.cpp)]

   Среда выполнения Windows использует полные имена для указания типов. `RuntimeClass_Windows_Foundation_Uri` Параметр — это строка, предоставляемая среда выполнения Windows и содержащая имя требуемого класса среды выполнения.

4. Инициализируйте переменную [Microsoft:: WRL:: оболочки:: HString](hstring-class.md) , которая представляет универсальный `"https://www.microsoft.com"`код ресурса (URI).

   [!code-cpp[wrl-consume-component#6](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_4.cpp)]

   В среда выполнения Windows не выделяется память для строки, которая будет использоваться среда выполнения Windows. Вместо этого среда выполнения Windows создает копию строки в буфере, который поддерживается и используется для операций, а затем возвращает маркер в созданный буфер.

5. Используйте метод фабрики `IUriRuntimeClassFactory::CreateUri` для создания объекта `ABI::Windows::Foundation::IUriRuntimeClass`.

   [!code-cpp[wrl-consume-component#7](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_5.cpp)]

6. Вызовите метод `IUriRuntimeClass::get_Domain` для получения значения свойства `Domain`.

   [!code-cpp[wrl-consume-component#8](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_6.cpp)]

7. Выведите доменное имя с символом перевода строки в окно консоли. Все объекты `ComPtr` и RAII покидают область действия и автоматически освобождаются.

   [!code-cpp[wrl-consume-component#9](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_7.cpp)]

   Функция [виндовсжетстрингравбуффер](/windows/win32/api/winstring/nf-winstring-windowsgetstringrawbuffer) извлекает базовую форму Юникода строки URI.

Ниже приведен полный пример.

[!code-cpp[wrl-consume-component#1](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_8.cpp)]

## <a name="compiling-the-code"></a>Компиляция кода

Чтобы скомпилировать код, скопируйте его и вставьте в проект Visual Studio или вставьте в файл с именем `wrl-consume-component.cpp` , а затем выполните следующую команду в окне командной строки Visual Studio.

`cl.exe wrl-consume-component.cpp runtimeobject.lib`

## <a name="see-also"></a>См. также

[Библиотека шаблонов C++ среды выполнения Windows (WRL)](windows-runtime-cpp-template-library-wrl.md)