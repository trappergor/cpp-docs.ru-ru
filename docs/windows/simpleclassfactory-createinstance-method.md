---
title: "Метод SimpleClassFactory::CreateInstance | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::SimpleClassFactory::CreateInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateInstance - метод"
ms.assetid: 17b7947a-2608-49d9-b730-fef76501c9bc
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод SimpleClassFactory::CreateInstance
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает экземпляр указанного интерфейса.  
  
## Синтаксис  
  
```  
  
STDMETHOD(  
   CreateInstance  
)  
   (_Inout_opt_ IUnknown* pUnkOuter,   
   REFIID riid,   
   _Deref_out_ void** ppvObject);  
```  
  
#### Параметры  
 `pUnkOuter`  
 Должно быть `nullptr`; в противном случае возвращается значение CLASS\_E\_NOAGGREGATION.  
  
 SimpleClassFactory не поддерживает агрегирование.  Если поддерживается агрегирование и создаваемый объект был частью агрегата, `pUnkOuter` будет указателем на управляющий интерфейс IUnknown агрегата.  
  
 `riid`  
 Идентификатор интерфейса объекта, который нужно создать.  
  
 `ppvObject`  
 Когда эта операция завершена, указатель на экземпляр объекта задается параметром `riid`.  
  
## Возвращаемое значение  
 Значение S\_ОК в случае успеха; в противном случае — значение HRESULT, указывающее на ошибку.  
  
## Примечания  
 Если \_\_WRL\_STRICT определено, выдается ошибка утверждения, если базовый класс, указанный в параметре шаблона класса, не является производным от класса [RuntimeClass](../windows/runtimeclass-class.md), или не настроен со значением ClassicCom или WinRtClassicComMix перечисления [RuntimeClassType](../windows/runtimeclasstype-enumeration.md).  
  
## Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс SimpleClassFactory](../windows/simpleclassfactory-class.md)