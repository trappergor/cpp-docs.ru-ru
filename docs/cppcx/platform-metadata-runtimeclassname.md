---
title: Platform::Metadata::RuntimeClassName | Документы Microsoft
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Metadata::RuntimeClassName
helpviewer_keywords:
- RuntimeClassName
- Platform::Metadata::RuntimeClassName
ms.assetid: fdef8f85-ab94-4edd-ba50-ee0da9358ff6
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 297a5089af7db43d837934e864e0925cd7b34a3d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33088236"
---
# <a name="platformmetadataruntimeclassname"></a>Platform::Metadata::RuntimeClassName
При применении к определению класса, проверяет, возвращает ли функция GetRuntimeClassName допустимое имя в закрытый класс.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
[Platform::Metadata::RuntimeClassName] name  
```  
  
#### <a name="parameters"></a>Параметры  
 имя  
  
 Имя существующего открытого типа, который виден в среде выполнения Windows.  
  
### <a name="remarks"></a>Примечания  
 Этот атрибут используется в закрытых классах ссылок для указания имени пользовательского типа среды выполнения. Задает в качестве имени открытый интерфейс, реализуемый классом.  
  
### <a name="example"></a>Пример  
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
  
## <a name="see-also"></a>См. также  
 [Пространство имен Platform::Metadata](../cppcx/platform-metadata-namespace.md)