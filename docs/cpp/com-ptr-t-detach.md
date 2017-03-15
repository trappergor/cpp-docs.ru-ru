---
title: "_com_ptr_t::Detach | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t::Detach"
  - "_com_ptr_t.Detach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Detach - метод"
ms.assetid: 0652053e-af37-44e9-a278-2522212ebfed
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_ptr_t::Detach
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Извлекает и возвращает инкапсулированный указатель на интерфейс.  
  
## Синтаксис  
  
```  
  
Interface* Detach( ) throw( );  
  
```  
  
## Заметки  
 Извлекает и возвращает инкапсулированный указатель на интерфейс, а затем очищает область хранения инкапсулированного указателя, присваивая ему значение **NULL**.  Поэтому указатель на интерфейс удаляется из инкапсуляции.  Решение о том, вызывать ли функцию **Release** для возвращенного указателя на интерфейс, принимает разработчик.  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Класс \_com\_ptr\_t](../cpp/com-ptr-t-class.md)