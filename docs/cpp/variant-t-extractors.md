---
title: "Средства извлечения _variant_t | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_variant_t.operatordouble"
  - "operatorlong"
  - "_variant_t::operator_bstr_t"
  - "operatordouble"
  - "_variant_t.operatorCY"
  - "operatorCY"
  - "_variant_t::operatorCY"
  - "_variant_t::operatordouble"
  - "operatorfloat"
  - "operatorBYTE"
  - "_variant_t.operatorDECIMAL"
  - "_variant_t::operatorlong"
  - "operatorIDispatch"
  - "_variant_t.operatorBYTE"
  - "operatorDECIMAL"
  - "_variant_t.operator_bstr_t"
  - "_variant_t::operatorDECIMAL"
  - "_variant_t.operatorIUnknown"
  - "_variant_t.operatorlong"
  - "_variant_t::operatorIDispatch"
  - "_variant_t::operatorIUnknown"
  - "operatorIUnknown"
  - "_variant_t.operatorbool"
  - "_variant_t::operatorBYTE"
  - "_variant_t.operatorfloat"
  - "operator_bstr_t"
  - "_variant_t::operatorbool"
  - "operatorshort"
  - "_variant_t::operatorshort"
  - "_variant_t::operatorfloat"
  - "_variant_t.operatorIDispatch"
  - "_variant_t.operatorshort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "средства извлечения, _variant_t - класс"
  - "_bstr_t - оператор"
  - "bool - оператор"
  - "BYTE - оператор"
  - "CY - оператор"
  - "DECIMAL - оператор"
  - "double - оператор"
  - "float - оператор"
  - "IDispatch - оператор"
  - "IUnknown - оператор"
  - "long - оператор"
  - "оператор SHORT"
ms.assetid: 33c1782f-045a-4673-9619-1d750efc83a9
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Средства извлечения _variant_t
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Извлечение данных из инкапсулированного объекта **VARIANT**.  
  
## Синтаксис  
  
```  
  
      operator short( ) const;   
operator long( ) const;   
operator float( ) const;   
operator double( ) const;   
operator CY( ) const;   
operator _bstr_t( ) const;   
operator IDispatch*( ) const;   
operator bool( ) const;   
operator IUnknown*( ) const;   
operator DECIMAL( ) const;   
operator BYTE( ) const;  
operator VARIANT() const throw();  
operator char() const;  
operator unsigned short() const;  
operator unsigned long() const;  
operator int() const;  
operator unsigned int() const;  
operator __int64() const;  
operator unsigned __int64() const;  
```  
  
## Заметки  
 Извлечение необработанных данных из инкапсулированного объекта **VARIANT**.  Если тип объекта **VARIANT** неправильный, для выполнения попытки преобразования используется **VariantChangeType**. В случае сбоя появляется ошибка.  
  
-   **operator short\( \)** извлекает целочисленное значение типа **short**.  
  
-   **operator long\( \)** извлекает целочисленное значение типа **long**.  
  
-   **operator float\( \)** извлекает целочисленное значение типа **float**.  
  
-   **operator double\( \)** извлекает целочисленное значение типа **double**.  
  
-   **operator CY\( \)** извлекает объект **CY**.  
  
-   **operator bool\( \)** извлекает значение типа `bool`.  
  
-   **operator DECIMAL\( \)** извлекает значение типа **DECIMAL**.  
  
-   **operator BYTE\( \)** извлекает значение типа **BYTE**.  
  
-   **operator \_bstr\_t\(\)** извлекает строку, инкапсулированную в объекте `_bstr_t`.  
  
-   **operator IDispatch\*\( \)** извлекает из инкапсулированного объекта **VARIANT** указатель на disp\-интерфейс.  Для результирующего указателя вызывается метод `AddRef`, поэтому для его освобождения следует вызвать метод **Release**.  
  
-   **operator IUnknown\*\( \)** извлекает из инкапсулированного объекта **VARIANT** указатель на COM\-интерфейс.  Для результирующего указателя вызывается метод `AddRef`, поэтому для его освобождения следует вызвать метод **Release**.  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Класс \_variant\_t](../cpp/variant-t-class.md)