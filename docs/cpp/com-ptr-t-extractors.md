---
title: "Средства извлечения _com_ptr_t | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t::operatorInterface&"
  - "operatorInterface*"
  - "operatorInterface&"
  - "_com_ptr_t::operatorbool"
  - "_com_ptr_t.operator->"
  - "_com_ptr_t.operator*"
  - "_com_ptr_t::operator->"
  - "_com_ptr_t::operator*"
  - "_com_ptr_t.operatorInterface&"
  - "_com_ptr_t.operatorbool"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "& - оператор, с конкретными объектами"
  - "* - оператор, с конкретными объектами"
  - "-> - оператор, с конкретными объектами"
  - "средства извлечения"
  - "средства извлечения, _com_ptr_t - класс"
  - "оператор *"
  - "bool - оператор"
  - "оператор Interface&"
  - "оператор Interface*"
  - "operator&"
  - "operator*"
  - "operator->"
ms.assetid: 194b9e0e-123c-49ff-a187-0a7fcd68145a
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Средства извлечения _com_ptr_t
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Извлекают инкапсулированный указатель на COM\-интерфейс.  
  
## Синтаксис  
  
```  
  
      operator Interface*( ) const throw( );   
operator Interface&( ) const;   
Interface& operator*( ) const;   
Interface* operator->( ) const;   
Interface** operator&( ) throw( );   
operator bool( ) const throw( );  
```  
  
## Заметки  
  
-   **operator Interface\*** Возвращает инкапсулированный указатель на интерфейс, который может иметь значение **NULL**.  
  
-   **operator Interface&** Возвращает ссылку на инкапсулированный указатель на интерфейс и создает ошибку, если указатель имеет значение **NULL**.  
  
-   **operator\*** При разыменовании позволяет объекту интеллектуального указателя функционировать так, как если бы он сам является инкапсулированным интерфейсом.  
  
-   **operator\-\>** При разыменовании позволяет объекту интеллектуального указателя функционировать так, как если бы он сам является инкапсулированным интерфейсом.  
  
-   **operator&** Освобождает любой инкапсулированный указатель на интерфейс, заменяя его значением **NULL**, и возвращает адрес инкапсулированного указателя.  Благодаря этому интеллектуальный указатель можно передавать по адресу в функцию с параметром **out**, через которую он возвращает указатель на интерфейс.  
  
-   **operator bool** Позволяет использовать объект интеллектуального указателя в условном выражении.  Этот оператор возвращает значение **true**, если указатель не **NULL**.  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Класс \_com\_ptr\_t](../cpp/com-ptr-t-class.md)