---
title: "Слабые ссылки и устранение циклов (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1acb6402-05f0-4951-af94-0e9dab41c53e
caps.latest.revision: 12
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 12
---
# Слабые ссылки и устранение циклов (C++/CX)
В любой системе типов, которая основана на подсчете ссылок, ссылки на типы могут сформировать *циклы*, т. е. может возникнуть ситуация, когда один объект ссылается на второй объект, второй объект ссылается на третий объект, и так далее до тех пор, пока некоторый последний объект не будет ссылаться на первый объект. В цикле объекты невозможно правильно удалить, если количество ссылок одного из объектов становится равным нулю. Чтобы решить эту проблему, в [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] имеется класс [Класс Platform::WeakReference](../cppcx/platform-weakreference-class.md). Объект `WeakReference` поддерживает метод [Resolve](../cppcx/weakreference-resolve-method-platform-namespace.md), который возвращает значение NULL, если объект больше не существует, или исключение [Platform::InvalidCastException](../cppcx/platform-invalidcastexception-class.md), если объект существует, но его тип отличается от  `T`.  
  
 Одна из ситуаций, в которой следует использовать `WeakReference`, — когда указатель `this` перехватывается в лямбда\-выражении, используемом для определения обработчика событий. Рекомендуется использовать при определении обработчиков событий именованные методы, но если необходимо использовать для обработчика событий лямбда\-выражения или если необходимо нарушить цикл подсчета ссылок, используйте класс `WeakReference`. Ниже приведен пример:  
  
```  
  
using namespace Platform::Details;  
using namespace Windows::UI::Xaml;  
using namespace Windows::UI::Xaml::Input;  
using namespace Windows::UI::Xaml::Controls;  
  
Class1::Class1()  
{  
    // Class1 has a reference to m_Page  
    m_Page = ref new Page();  
  
    // m_Page will have a reference to this Class1  
    // so create a weak reference to this  
    WeakReference wr(this);  
    m_Page->DoubleTapped += ref new DoubleTappedEventHandler(   
        [wr](Object^ sender, DoubleTappedRoutedEventArgs^ args)  
    {  
       // Use the weak reference to get the object  
       Class1^ c = wr.Resolve<Class1>();  
       if (c != nullptr)  
       {  
           c->m_eventFired = true;  
       }  
       else  
       {  
           // Inform the event that this handler should be removed  
           // from the subscriber list  
           throw ref new DisconnectedException();  
       }  
    });   
}  
  
}  
```  
  
 Когда обработчик событий создает исключение `DisconnectedException`, событие удаляет обработчик из списка подписчиков.  
  
## См. также  
 [\(NOTINBUILD\) Дополнительные разделы](http://msdn.microsoft.com/ru-ru/1ccff0cf-a6cc-47ef-a05f-eba6307b3ced)