---
title: "_bstr_t::operator +=, + | Microsoft Docs"
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
  - "_bstr_t::operator+"
  - "_bstr_t::operator+="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "+ - оператор, _bstr_t - объекты"
  - "+= - оператор, дополнение строк"
ms.assetid: d28316ce-c2c8-4a38-bdb3-44fa4e582c44
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _bstr_t::operator +=, +
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Добавляет символы в конец объекта `_bstr_t` или объединяет две строки.  
  
## Синтаксис  
  
```  
  
      _bstr_t& operator+=(  
   const _bstr_t& s1   
);  
_bstr_t operator+(  
   const _bstr_t& s1   
);  
friend _bstr_t operator+(  
   const char* s2,  
   const _bstr_t& s1   
);  
friend _bstr_t operator+(  
   const wchar_t* s3,  
   const _bstr_t& s1   
);  
```  
  
#### Параметры  
 *s1*  
 Объект `_bstr_t`.  
  
 *s2*  
 Многобайтовая строка.  
  
 `s3`  
 Строка Юникода.  
  
## Заметки  
 Эти операторы выполняют объединение строк:  
  
-   **operator\+\=\(**  *s1*  **\)** Добавляет символы из инкапсулированного `BSTR` строки *s1* в конец инкапсулированного `BSTR` этого объекта.  
  
-   **operator\+\(**  *s1*  **\)** Возвращает новый `_bstr_t`, который образуется путем объединения `BSTR` этого объекта с таковым строки *s1*.  
  
-   **оператор\+\(**  *s2*  **&#124;**  *s1*  **\)** Возвращает новый `_bstr_t`, который образуется путем объединения многобайтовой строки *s2*, преобразованной в Юникод, с `BSTR`, инкапсулированным в строку *s1*.  
  
-   **operator\+\(**  `s3` **,**  *s1*  **\)** Возвращает новый `_bstr_t`, который образуется путем объединения строки Юникод `s3` с `BSTR`, инкапсулированным в строку *s1*.  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Класс \_bstr\_t](../cpp/bstr-t-class.md)