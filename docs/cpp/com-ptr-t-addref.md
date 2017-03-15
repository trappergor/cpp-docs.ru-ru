---
title: "_com_ptr_t::AddRef | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t::AddRef"
  - "_com_ptr_t.AddRef"
  - "AddRef"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddRef - метод [C++], указатели интерфейса"
ms.assetid: c104dac3-aad3-40bb-a298-75c6cd0e63a2
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_ptr_t::AddRef
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Вызывает функцию\-член `AddRef` **IUnknown** в инкапсулированном указателе на интерфейс.  
  
## Синтаксис  
  
```  
  
void AddRef( );  
  
```  
  
## Заметки  
 Вызывает `IUnknown::AddRef` в инкапсулированном указателе на интерфейс, создавая ошибку `E_POINTER`, если этот указатель имеет значение **NULL**.  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Класс \_com\_ptr\_t](../cpp/com-ptr-t-class.md)