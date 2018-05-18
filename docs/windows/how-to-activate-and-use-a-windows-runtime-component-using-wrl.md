---
title: 'Как: активация и использование компонента среды выполнения Windows, с использованием WRL | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 54828f02-6af3-45d1-b965-d0104442f8d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 50c37438bf3a840f57119245b845d0b94f1873db
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="how-to-activate-and-use-a-windows-runtime-component-using-wrl"></a>Практическое руководство. Активация и использование компонента среды выполнения Windows с помощью WRL
В этом документе показано, как использовать среды выполнения C++ шаблон библиотеки Windows (WRL) для инициализации среды выполнения Windows и как активация и использование компонента среды выполнения Windows.  
  
 Для использования компонента необходимо получить указатель интерфейса на тип, который реализуется компонентом. И поскольку лежащие в основе среды выполнения Windows модели объектов компонентов (COM), необходимо соблюдать правила модели COM для поддержки экземпляра типа. Например, необходимо поддерживать *количество ссылок* , определяющий, когда тип удаляется из памяти.  
  
 Чтобы упростить использование среды выполнения Windows, библиотека шаблонов C++ среды выполнения Windows предоставляет шаблон интеллектуального указателя [ComPtr\<T >](../windows/comptr-class.md), который автоматически выполняет подсчет ссылок. При объявлении переменной необходимо указать `ComPtr<` *имя интерфейса* `>` *идентификатор*. Для обращения к членам интерфейса примените оператор доступа к членам класса в виде стрелки (`->`) к идентификатору.  
  
> [!IMPORTANT]
>  При вызове функции интерфейса необходимо всегда проверять возвращаемое значение `HRESULT`.  
  
## <a name="activating-and-using-a-windows-runtime-component"></a>Активация и использование компонента среды выполнения Windows  
 В следующих шагах используется `Windows::Foundation::IUriRuntimeClass` интерфейс для демонстрации создания фабрики активации компонента среды выполнения Windows, создания экземпляра этого компонента и извлечь значение свойства. Они также показано, как инициализировать среду выполнения Windows. Далее приведен полный пример.  
  
> [!IMPORTANT]
>  Несмотря на то, что обычно используется библиотека шаблонов C++ среды выполнения Windows в приложении универсальной платформы Windows (UWP), в этом примере используется консольное приложение для иллюстрации. Функции, такие как `wprintf_s` не доступны из приложения UWP. Дополнительные сведения о типах и функции, которые можно использовать в приложении UWP в разделе [функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) и [Win32 и COM для приложений UWP](/uwp/win32-and-com/win32-and-com-for-uwp-apps).  
  
#### <a name="to-activate-and-use-a-windows-runtime-component"></a>Активация и использование компонента среды выполнения Windows  
  
1.  Включить (`#include`) все необходимые среды выполнения Windows, библиотека шаблонов C++ среды выполнения Windows или заголовков стандартной библиотеки C++.  
  
     [!code-cpp[wrl-consume-component#2](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_1.cpp)]  
  
     Рекомендуется использовать директиву `using namespace` в CPP-файле, чтобы сделать код более удобочитаемым.  
  
2.  Инициализируйте поток, в котором выполняется приложение. Каждое приложение должно инициализировать свой поток и потоковую модель. В этом примере используется [Microsoft::WRL::Wrappers::RoInitializeWrapper](../windows/roinitializewrapper-class.md) класса для инициализации среды выполнения Windows и указывает [RO_INIT_MULTITHREADED](http://msdn.microsoft.com/library/windows/apps/br224661.aspx) как потоковую модель. Класс `RoInitializeWrapper` вызывает `Windows::Foundation::Initialize` при создании и `Windows::Foundation::Uninitialize` при удалении.  
  
     [!code-cpp[wrl-consume-component#3](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_2.cpp)]  
  
     Во втором операторе [RoInitializeWrapper::HRESULT](../windows/roinitializewrapper-hresult-parens-operator.md) оператор возвращает `HRESULT` из вызова `Windows::Foundation::Initialize`.  
  
3.  Создание *фабрики активации* для `ABI::Windows::Foundation::IUriRuntimeClassFactory` интерфейса.  
  
     [!code-cpp[wrl-consume-component#4](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_3.cpp)]  
  
     Среда выполнения Windows использует полные имена для определения типов. `RuntimeClass_Windows_Foundation_Uri` Параметр представляет собой строку, предоставляемые средой выполнения Windows и содержит имя класса необходимая среда выполнения.  
  
4.  Инициализация [Microsoft::WRL::Wrappers::HString](../windows/hstring-class.md) переменной, представляющей URI `"http://www.microsoft.com"`.  
  
     [!code-cpp[wrl-consume-component#6](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_4.cpp)]  
  
     В среде выполнения Windows нет необходимости выделять память для строки, который будет использовать среды выполнения Windows. Вместо этого среда выполнения Windows создает копию строки в буфере, он сохраняет и использует для операций и затем возвращает дескриптор буфера он создан.  
  
5.  Используйте метод фабрики `IUriRuntimeClassFactory::CreateUri` для создания объекта `ABI::Windows::Foundation::IUriRuntimeClass`.  
  
     [!code-cpp[wrl-consume-component#7](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_5.cpp)]  
  
6.  Вызовите метод `IUriRuntimeClass::get_Domain` для получения значения свойства `Domain`.  
  
     [!code-cpp[wrl-consume-component#8](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_6.cpp)]  
  
7.  Выведите доменное имя с символом перевода строки в окно консоли. Все объекты `ComPtr` и RAII покидают область действия и автоматически освобождаются.  
  
     [!code-cpp[wrl-consume-component#9](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_7.cpp)]  
  
     [WindowsGetStringRawBuffer](http://msdn.microsoft.com/library/windows/apps/br224636.aspx) функция получает базовый формат Юникода в строке URI.  
  
 Ниже приведен полный пример.  
  
 [!code-cpp[wrl-consume-component#1](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_8.cpp)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы скомпилировать код, скопируйте его и затем вставьте его в проект Visual Studio или в файл с именем `wrl-consume-component.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **CL.exe wrl-consume-component.cpp runtimeobject.lib**  
  
## <a name="see-also"></a>См. также  
 [Библиотека шаблонов C++ среды выполнения Windows (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)