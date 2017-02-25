---
title: "Практическое руководство. Активация и использование компонента среды выполнения Windows с помощью WRL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 54828f02-6af3-45d1-b965-d0104442f8d5
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# Практическое руководство. Активация и использование компонента среды выполнения Windows с помощью WRL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Этот документ показывает, как использовать [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] \([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\) для инициализации [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] и как активировать и использовать компонент [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
> [!NOTE]
>  В этом примере активируется встроенный компонент [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  Чтобы получить сведения о том, как создать собственный компонент, который можно активировать таким же образом, см. [Пошаговое руководство. Создание базового компонента среды выполнения Windows](../windows/walkthrough-creating-a-basic-windows-runtime-component-using-wrl.md).  
  
 Для использования компонента необходимо получить указатель интерфейса к типу, реализованному компонентом.  А поскольку основной технологией [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] является модель Component Object Model \(COM\), необходимо соблюдать правила модели COM для поддержки экземпляра типа.  Например, необходимо поддерживать *счетчик ссылок*, определяющий, когда тип удаляется из памяти.  
  
 Для упрощения использования [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] предоставляет шаблон интеллектуального указателя, [ComPtr\<T\>](../windows/comptr-class.md), который автоматически выполняет подсчет ссылок.  При объявлении переменной укажите `ComPtr<`*interface\-name*`>` *identifier*.  Для обращения к членам интерфейса примените оператор доступа к членам класса в виде стрелки \(`->`\) к идентификатору.  
  
> [!IMPORTANT]
>  При вызове функции интерфейса необходимо всегда проверять возвращаемое значение `HRESULT`.  
  
## Активирование и использование компонента среды выполнения Windows  
 Следующие шаги используют интерфейс `Windows::Foundation::IUriRuntimeClass` для демонстрации создания фабрики активации компонента [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], создания экземпляра этого компонента и извлечения значения свойства.  Они также показывают, как инициализировать [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  Полный пример кода выглядит следующим образом.  
  
> [!IMPORTANT]
>  Хотя обычно используется [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] в приложении [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)], в этом образце для иллюстрации используется консольное приложение.  Функции, такие как `wprintf_s`, недоступны из приложения [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)].  Дополнительные сведения о типах и функциях, которые можно использовать в приложении [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] см. [Функции CRT, не поддерживаемые \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx) и [Win32 и модели COM для приложений Магазина Windows](http://msdn.microsoft.com/library/windows/apps/br205757.aspx).  
  
#### Активация и использование компонента среды выполнения Windows  
  
1.  Включите \(`#include`\) все необходимые заголовки [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] или стандартной библиотеки C\+\+.  
  
     [!CODE [wrl-consume-component#2](../CodeSnippet/VS_Snippets_Misc/wrl-consume-component#2)]  
  
     Рекомендуется использовать директиву `using namespace` в CPP\-файле, чтобы сделать код более удобочитаемым.  
  
2.  Инициализируйте поток, в котором выполняется приложение.  Каждое приложение должно инициализировать его поток и потоковую модель.  В этом примере используется класс [Microsoft::WRL::Wrappers::RoInitializeWrapper](../Topic/RoInitializeWrapper%20Class.md) для инициализации [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] и определения [RO\_INIT\_MULTITHREADED](http://msdn.microsoft.com/library/windows/apps/br224661.aspx) в качестве потоковой модели.  Класс `RoInitializeWrapper` вызывает `Windows::Foundation::Initialize` при построении и `Windows::Foundation::Uninitialize` при уничтожении.  
  
     [!CODE [wrl-consume-component#3](../CodeSnippet/VS_Snippets_Misc/wrl-consume-component#3)]  
  
     Во второй инструкции оператор [RoInitializeWrapper::HRESULT](../windows/roinitializewrapper-hresult-parens-operator.md) возвращает `HRESULT` из вызова `Windows::Foundation::Initialize`.  
  
3.  Создайте *фабрику активации* для интерфейса `ABI::Windows::Foundation::IUriRuntimeClassFactory`.  
  
     [!CODE [wrl-consume-component#4](../CodeSnippet/VS_Snippets_Misc/wrl-consume-component#4)]  
  
     В [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] используются полные имена для идентификации типов.  Параметр `RuntimeClass_Windows_Foundation_Uri` является строкой, предоставляемой [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], которая содержит требуемое имя класса среды выполнения.  
  
4.  Используйте переменную [Microsoft::WRL::Wrappers::HString](../windows/hstring-class.md), представляющую универсальный код ресурса \(URI\) `"http://www.microsoft.com"`.  
  
     [!CODE [wrl-consume-component#6](../CodeSnippet/VS_Snippets_Misc/wrl-consume-component#6)]  
  
     В [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] нет необходимости выделять память для строки, которую [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] будет использовать.  Вместо этого [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] создает копию строки в буфере, который он поддерживает и использует для операций, а затем возвращает дескриптор созданного буфера.  
  
5.  Используйте фабричный метод `IUriRuntimeClassFactory::CreateUri` для создания объекта `ABI::Windows::Foundation::IUriRuntimeClass`.  
  
     [!CODE [wrl-consume-component#7](../CodeSnippet/VS_Snippets_Misc/wrl-consume-component#7)]  
  
6.  Вызовите метод `IUriRuntimeClass::get_Domain` для получения значения свойства `Domain`.  
  
     [!CODE [wrl-consume-component#8](../CodeSnippet/VS_Snippets_Misc/wrl-consume-component#8)]  
  
7.  Введите доменное имя в консоль и нажмите 'ВВОД'  Все объекты `ComPtr` и RAII покидают область действия и автоматически освобождаются.  
  
     [!CODE [wrl-consume-component#9](../CodeSnippet/VS_Snippets_Misc/wrl-consume-component#9)]  
  
     Функция [WindowsGetStringRawBuffer](http://msdn.microsoft.com/library/windows/apps/br224636.aspx) извлекает основную форму в кодировке Юникод строки универсального кода ресурса \(URI\).  
  
 Ниже приведен полный пример.  
  
 [!CODE [wrl-consume-component#1](../CodeSnippet/VS_Snippets_Misc/wrl-consume-component#1)]  
  
## Компиляция кода  
 Чтобы скомпилировать код, скопируйте и вставьте его в проект Visual Studio или в файл с именем `wrl-consume-component.cpp`, а затем выполните в окне командной строки Visual Studio следующую команду.  
  
 **cl.exe wrl\-consume\-component.cpp runtimeobject.lib**  
  
## См. также  
 [Библиотека шаблонов C\+\+ среды выполнения Windows \(WRL\)](../Topic/Windows%20Runtime%20C++%20Template%20Library%20\(WRL\).md)