---
title: "Platform::Metadata::RuntimeClassName | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Metadata::RuntimeClassName"
helpviewer_keywords: 
  - "RuntimeClassName"
  - "Platform::Metadata::RuntimeClassName"
ms.assetid: fdef8f85-ab94-4edd-ba50-ee0da9358ff6
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 2
---
# Platform::Metadata::RuntimeClassName
При применении к определению класса, проверяет, возвращает ли функция GetRuntimeClassName допустимое имя в закрытый класс.  
  
## Синтаксис  
  
```vb  
[Platform::Metadata::RuntimeClassName] name  
```  
  
#### Параметры  
 имя  
  
 Имя существующего открытого типа, который виден в среде выполнения Windows.  
  
## Заметки  
 Этот атрибут используется в закрытых классах ссылок для указания имени пользовательского типа среды выполнения. Задает в качестве имени открытый интерфейс, реализуемый классом.  
  
## Пример  
 В следующем примере показано использование атрибута. В этом примере имя типа среды выполнения HellowWorldImpl является интерфейсом Test::Native::MyComponent::IHelloWorld.  
  
```  
  
namespace Test  
{  
    namespace Native  
    {  
        namespace MyComponent  
        {  
            public interface class IHelloWorld  
            {  
                Platform::String^ SayHello();  
            };  
  
            private ref class HelloWorldImpl sealed :[Platform::Metadata::RuntimeClassName] IHelloWorld  
            {  
            public:  
                HelloWorldImpl();  
                virtual Platform::String^ SayHello();  
            };  
  
            Platform::String^ HelloWorldImpl::SayHello()  
            {  
                return L"Hello World!";  
            }  
        }  
    }  
}  
```  
  
## См. также  
 [Пространство имен Platform::Metadata](../cppcx/platform-metadata-namespace.md)