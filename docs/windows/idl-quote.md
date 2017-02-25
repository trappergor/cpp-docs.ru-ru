---
title: "idl_quote | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.idl_quote"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "idl_quote attribute"
ms.assetid: a370e1b7-948b-4e67-9a25-58facf24e4c9
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# idl_quote
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Позволяет конструкциям языка IDL использования, которые не поддерживаются в текущей версии Visual C\+\+ и передать их к созданному файлу idl.  
  
## Синтаксис  
  
```  
  
      [ idl_quote(  
   text  
) ]  
```  
  
#### Параметры  
 *текст*  
 Имя атрибута, который планируется компилятора Visual C\+\+, чтобы передать к созданному idl\-файл без возвращения ошибки компилятора.  
  
## Заметки  
 Если **idl\_quote** Атрибут C\+\+ используется как отдельный атрибут \(точкой с запятой после заключительного брекета\), после чего Текст помещает в объединенном файле idl как.  If **idl\_quote** использует на символе, Текст помещает в блоке атрибута символов.  
  
## Пример  
 В следующем примере кода показано, как можно определить неподдерживаемый атрибут \(использование INподдерживаются\), и как определять и использовать конструкцию неопределенное idl.  
  
```  
// cpp_attr_ref_idl_quote.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLibrary")];  
  
[export]  
struct MYFLOT {  
   int i;  
};  
  
[export]  
struct MYDUB {  
   int i;  
};  
  
[idl_quote("typedef union _S1_TYPE switch (long l1) U1_TYPE { case 1024: \  
struct MYFLOT f1; case 2048: struct MYDUB d2; } S1_TYPE;") ];  
  
typedef struct _S1_TYPE {   
   long l1;   
  
union {   
   MYFLOT f1; MYDUB d2; } U1_TYPE;   
} S1_TYPE;  
  
[uuid("2F5F63F1-16DA-11d2-9E7B-00C04FB926DA"), object]  
__interface IStatic{  
   HRESULT Func1([idl_quote("in")] int i);  
   HRESULT func( S1_TYPE* myStruct );  
};  
```  
  
 Этот код вызывает MYFLOT и MYDUB и *Текст* запись, который необходимо поместить в созданном файле idl.  *Имя* параметр вынуждает *Текст* располагаться перед любым, который ссылается на *Имя* в созданном файле idl.  *зависимости* параметр вынуждает определения списка зависимостей располагаться выше *Текст* в созданном файле idl.  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Любой|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|None|  
|**Недопустимые атрибуты**|None|  
  
 Дополнительные сведения см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Stand\-Alone Attributes](../Topic/Stand-Alone%20Attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)