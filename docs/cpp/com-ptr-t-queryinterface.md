---
title: "_com_ptr_t::QueryInterface | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t::QueryInterface"
  - "_com_ptr_t.QueryInterface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "QueryInterface - метод"
ms.assetid: d03292f1-6b02-40db-9756-8b0837a97319
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_ptr_t::QueryInterface
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Вызывает функцию\-член `QueryInterface` **IUnknown** в инкапсулированном указателе на интерфейс.  
  
## Синтаксис  
  
```  
  
      template<typename _InterfaceType> HRESULT QueryInterface (  
   const IID& iid,  
   _InterfaceType*& p   
) throw ( );  
template<typename _InterfaceType> HRESULT QueryInterface (  
   const IID& iid,  
   _InterfaceType** p  
) throw( );  
```  
  
#### Параметры  
 `iid`  
 **IID** указателя на интерфейс.  
  
 `p`  
 Необработанный указатель на интерфейс.  
  
## Заметки  
 Вызывает **IUnknown::QueryInterface** для инкапсулированного указателя на интерфейс с заданным **IID** и возвращают необработанный результирующий указатель на интерфейс в параметре `p`.  Эта процедура возвращает значение `HRESULT`, которое указывает успешность или сбой выполнения.  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Класс \_com\_ptr\_t](../cpp/com-ptr-t-class.md)