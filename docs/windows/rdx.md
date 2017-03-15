---
title: "rdx | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.rdx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rdx attribute"
ms.assetid: ff8e4312-c1ad-4934-bdaa-86f54409651e
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# rdx
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает раздел реестра или изменяет существующий раздел реестра.  
  
## Синтаксис  
  
```  
  
      [ rdx(   
   key,   
   valuename=NULL,   
   regtype   
) ]  
```  
  
#### Параметры  
 `key`  
 Имя открытого ключа, который требуется создать.  
  
 `valuename`\(необязательно\)  
 Определяет поле значение.  Если поле значения с таким именем еще не существует ключа, то он добавляется.  
  
 *regtype*  
 Тип добавляемого раздела реестра.  Может быть одно из следующих действий: **Текст**"  **dword**"  **binary**или  `CString`.  
  
## Заметки  
 **rdx** Атрибут C\+\+ создает или изменяет существующий раздел реестра для компонента COM.  Добавляет макрос атрибута BEGIN\_RDX\_MAP на объект, реализующий члена целевого объекта.  `RegistryDataExchange`функцию макроса, впрыснутую в результате BEGIN\_RDX\_MAP, можно использовать для передачи данных между реестре и элементами данных  
  
 Этот атрибут может использоваться совместно с [CoClass](../windows/coclass.md)"  [идентификатор progid](../Topic/progid.md)или  [vi\_progid](../windows/vi-progid.md) атрибуты или другие атрибуты, подразумевается одно из них.  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**класс** OR  `struct` элемент|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|None|  
|**Недопустимые атрибуты**|None|  
  
 Дополнительные сведения о контекстах атрибута см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## Пример  
 Следующий код добавляет называемый раздел реестра MyValue к системе, описывающие компонент COM CMyClass.  
  
```  
// cpp_attr_ref_rdx.cpp  
// compile with: /LD /link /OPT:NOREF  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
  
[module (name="MyLib")];  
  
class CMyClass {  
public:  
   CMyClass() {  
      strcpy_s(m_sz, "SomeValue");  
   }  
  
   [ rdx(key = "HKCR\\MyApp.MyApp.1", valuename = "MyValue", regtype = "text")]   
   char m_sz[256];  
};  
```  
  
## См. также  
 [COM Attributes](../Topic/COM%20Attributes.md)   
 [registration\_script](../windows/registration-script.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)