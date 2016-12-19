---
title: "_bstr_t::copy | Microsoft Docs"
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
  - "_bstr_t::copy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BSTR - объект, копировать"
  - "Copy - метод"
ms.assetid: 00ba7311-e82e-4a79-8106-5329fa2f869a
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _bstr_t::copy
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Создает копию инкапсулированного объекта `BSTR`.  
  
## Синтаксис  
  
```  
  
      BSTR copy(  
  bool fCopy = true  
) const;  
```  
  
#### Параметры  
 `fCopy`  
 Если имеет значение **true**, то метод **copy** возвращает копию содержащегося объекта `BSTR`; в противном случае метод **copy** возвращает фактический объект BSTR.  
  
## Заметки  
 Возвращает копию инкапсулированного объекта `BSTR`, для которого выделена память.  
  
## Пример  
  
```  
STDMETHODIMP CAlertMsg::get_ConnectionStr(BSTR *pVal){ //  m_bsConStr is _bstr_t  
   *pVal = m_bsConStr.copy();  
}  
```  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Класс \_bstr\_t](../cpp/bstr-t-class.md)