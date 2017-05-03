---
title: "Исключения (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6cbdc1f1-e4d7-4707-a670-86365146432f
caps.latest.revision: 22
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 22
---
# Исключения (C++/CX)
Обработка ошибок в [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\) основана на исключениях. На самом базовом уровне компоненты [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] сообщают об ошибках с помощью значений HRESULT. В [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] эти значения преобразуются в строго типизированные исключения, которые содержат значение HRESULT и, в [!INCLUDE[win81](../cppcx/includes/win81-md.md)], в строковое описание, доступное программным образом.  Исключения реализованы как классы `ref class`, производные от класса `Platform::Exception`.  В пространстве имен `Platform` определены отдельные классы исключений для наиболее часто встречающихся значений HRESULT. Все остальные значения передаются через класс `Platform::COMException`. Все классы исключений имеют [свойство Exception::HResult](../cppcx/exception-hresult-property.md), которое можно использовать для получения исходного значения HRESULT. В [!INCLUDE[win81](../cppcx/includes/win81-md.md)] также можно просматривать сведения о стеке вызовов пользовательского кода в отладчике, что позволяет точно определять источник исключения, даже если он находится в коде, написанном на языке, отличном от C\+\+.  
  
## Исключения  
 В программе, написанной на C\+\+, можно вызывать и перехватывать исключения, поступающие от операций [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], а также исключения, производные от класса `std::exception` и производные от пользовательского типа. Исключение [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] необходимо вызвать, только если оно пересекает границы интерфейса ABI \(например, если код, который перехватывает это исключение, написан на языке JavaScript\). Когда исключение C\+\+, не являющееся исключением [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], достигает границы интерфейса ABI, оно преобразуется в исключение `Platform::FailureException`, которое представляет значение HRESULT E\_FAIL. Дополнительные сведения об интерфейсе ABI см. в разделе [Создание компонентов среды выполнения Windows в C\+\+](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf).  
  
 Можно объявить класс [Platform::Exception](../cppcx/platform-exception-class.md) с использованием одного или двух конструкторов, принимающих параметр HRESULT либо параметры HRESULT и [Platform::String](../cppcx/platform-string-class.md)^, которые можно передать через интерфейс ABI любому обрабатывающему их приложению для Магазина Windows. Либо можно объявить исключение, воспользовавшись одним из двух перегрузок [метода Exception::CreateException](../cppcx/exception-createexception-method.md), которые могут принимать параметр HRESULT или параметры HRESULT и `Platform::String^`.  
  
## Стандартные исключения  
 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] поддерживает набор стандартных исключений, которые представляют типичные ошибки HRESULT. Каждое стандартное исключение наследуется от класса [Platform::COMException](../cppcx/platform-comexception-class.md), который, в свою очередь, наследуется от `Platform::Exception`. Если вы вызываете исключение через границы интерфейса ABI, оно должно быть одним из стандартных исключений.  
  
 Делать собственные типы исключений производными от класса `Platform::Exception` не допускается. Чтобы создать пользовательское исключение, используйте определяемое пользователем значение HRESULT для создания объекта `COMException`.  
  
 В следующей таблице перечислены стандартные исключения.  
  
|Имя|Значение HRESULT|Описание|  
|---------|----------------------|--------------|  
|COMException|*определяемое пользователем значение hresult*|Возникает при возвращении неизвестного значения HRESULT после вызова метода COM.|  
|AccessDeniedException|E\_ACCESSDENIED|Возникает при запрете доступа к ресурсу или функции.|  
|ChangedStateException|E\_CHANGED\_STATE|Возникает, если метод итератора коллекции или представления коллекции вызван после изменения родительской коллекции, что делает результаты метода недействительными.|  
|ClassNotRegisteredException|REGDB\_E\_CLASSNOTREG|Возникает, если COM\-класс не зарегистрирован.|  
|DisconnectedException|RPC\_E\_DISCONNECTED|Возникает, если объект отключен от своих клиентов.|  
|FailureException|E\_FAIL|Возникает, если операция завершается неудачно.|  
|InvalidArgumentException|E\_INVALIDARG|Вызывается, если один из передаваемых методу аргументов является недопустимым.|  
|InvalidCastException|E\_NOINTERFACE|Возникает, если тип не удается привести к другому типу.|  
|NotImplementedException|E\_NOTIMPL|Возникает, если метод интерфейса не реализован в классе.|  
|NullReferenceException|E\_POINTER|Возникает при попытке разыменовать ссылку на объект NULL.|  
|ObjectDisposedException|RO\_E\_CLOSED|Вызывается при выполнении операции над ликвидированным объектом.|  
|OperationCanceledException|E\_ABORT|Возникает при отмене операции.|  
|OutOfBoundsException|E\_BOUNDS|Возникает, когда операция пытается получить доступ к данным за пределами допустимого диапазона.|  
|OutOfMemoryException|E\_OUTOFMEMORY|Возникает, если недостаточно памяти для выполнения операции.|  
|WrongThreadException|RPC\_E\_WRONG\_THREAD|Вызывается, если поток выполняет вызов посредством указателя на интерфейс для прокси\-объекта, который не принадлежит к подразделению потока.|  
  
## Свойства HResult и Message  
 Все исключения имеют свойство [HResult](../cppcx/comexception-hresult-property.md) и свойство [Message](../cppcx/comexception-message-property.md). Свойство [Exception::HResult](../cppcx/exception-hresult-property.md) получает базовое числовое значение HRESULT соответствующего исключения. Свойство [Exception::Message](../cppcx/exception-message-property.md) получает предоставленную системой строку с описанием исключения. В [!INCLUDE[win8](../cppcx/includes/win8-md.md)] сообщение доступно только в отладчике и только для чтения. Это означает, что его невозможно изменить после повторного создания исключения. В [!INCLUDE[win81](../cppcx/includes/win81-md.md)] строку сообщения можно открыть программными средствами и указать новое сообщение, если необходимо заново создать исключение. В отладчике доступны более подробные данные стеков вызовов, включая данные об асинхронных вызовах методов.  
  
## Примеры  
 В этом примере показано, как вызвать исключение [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] для синхронных операций:  
  
 [!code-cpp[cx_exceptions#01](../snippets/cpp/VS_Snippets_Misc/cx_exceptions/cpp/class1.cpp#01)]  
  
 В следующем пример показано, как перехватить исключение.  
  
 [!code-cpp[cx_exceptions#02](../snippets/cpp/VS_Snippets_Misc/cx_exceptions/cpp/class1.cpp#02)]  
  
 Для перехвата исключений, создаваемых во время асинхронной операции, используйте класс задачи и добавьте продолжение обработки ошибок. Продолжение обработки ошибок маршалирует исключения, вызванные в других потоках, обратно вызывающему потоку, что позволяет обрабатывать все возможные исключения в одной структурной единице кода. Дополнительные сведения см. в статье [Асинхронное программирование в C\+\+](http://msdn.microsoft.com/library/windows/apps/Hh780559.aspx).  
  
## Событие UnhandledErrorDetected  
 В [!INCLUDE[win81](../cppcx/includes/win81-md.md)] можно подписаться на статическое событие [Windows::ApplicationModel::Core::CoreApplication::UnhandledErrorDetected](http://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.core.coreapplication.unhandlederrordetected.aspx), которое предоставляет доступ к необработанным ошибкам, приводящим к остановке процесса. Независимо от того, где возникла ошибка, она достигнет этого обработчика в виде объекта [Windows::ApplicationModel::Core::UnhandledError](http://msdnstage.redmond.corp.microsoft.com/library/windows/apps/windows.applicationmodel.core.unhandlederror.aspx), который передается с аргументами события. При вызове метода `Propagate` для объекта он создает исключение `Platform::*Exception` типа, соответствующего коду ошибки. В блоках catch можно при необходимости сохранить состояние пользователя, а затем либо разрешить завершение процесса путем вызова `throw`, либо каким\-либо образом вернуть программу в известное состояние. В следующем примере демонстрируется использование основного подхода:  
  
```  
  
// In app.xaml.h:  
void OnUnhandledException(Platform::Object^ sender, Windows::ApplicationModel::Core::UnhandledErrorDetectedEventArgs^ e);  
  
// In app.xaml.cpp  
  
// Subscribe to the event, for example in the app class constructor:  
Windows::ApplicationModel::Core::CoreApplication::UnhandledErrorDetected += ref new EventHandler<UnhandledErrorDetectedEventArgs^>(this, &App::OnUnhandledException);  
  
// Event handler implementation:  
void App::OnUnhandledException(Platform::Object^ sender, Windows::ApplicationModel::Core::UnhandledErrorDetectedEventArgs^ e)  
{  
    auto err = e->UnhandledError;  
  
    if (!err->Handled) //Propagate has not been called on it yet.  
{  
     try  
    {  
        err->Propagate();  
    }  
    // Catch any specific exception types if you know how to handle them  
    catch (AccessDeniedException^ ex)  
    {  
        // TODO: Log error and either take action to recover  
        // or else re-throw exception to continue fail-fast  
    }  
  
}  
  
```  
  
## Примечания  
 В [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] предложение `finally` не используется.  
  
## См. также  
 [Справочник по языку C\+\+](../cppcx/visual-c-language-reference-c-cx.md)   
 [Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)