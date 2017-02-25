---
title: "Метод SimpleActivationFactory::GetRuntimeClassName | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName"
dev_langs: 
  - "C++"
ms.assetid: 3aa07487-9a42-46f8-8893-37ba6315e50b
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Метод SimpleActivationFactory::GetRuntimeClassName
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Получает имя класса среды выполнения экземпляра класса, указанного в параметре шаблона класса `Base`.  
  
## Синтаксис  
  
```  
STDMETHOD(  
   GetRuntimeClassName  
)(_Out_ HSTRING* runtimeName);  
```  
  
#### Параметры  
 `runtimeName`  
 Когда эта операция завершится, имя класса среды выполнения.  
  
## Возвращаемое значение  
 Значение S\_ОК в случае успеха; в противном случае — значение HRESULT, указывающее на ошибку.  
  
## Примечания  
 Если \_\_WRL\_STRICT определено, выдается ошибка утверждения, если класс, указанный в параметре шаблона класса `Base`, не является производным от класса [RuntimeClass](../windows/runtimeclass-class.md), или не настроен со значением WinRt или WinRtClassicComMix перечисления [RuntimeClassType](../windows/runtimeclasstype-enumeration.md).  
  
## Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс SimpleActivationFactory](../windows/simpleactivationfactory-class.md)