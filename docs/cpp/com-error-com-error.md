---
title: "_com_error::_com_error | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_error._com_error"
  - "_com_error::_com_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_com_error - метод"
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_error::_com_error
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Создает объект `_com_error`.  
  
## Синтаксис  
  
```  
  
      _com_error(  
   HRESULT hr,  
   IErrorInfo* perrinfo = NULL,  
   bool fAddRef=false  
) throw( );  
_com_error(  
   const _com_error& that   
) throw( );  
```  
  
#### Параметры  
 `hr`  
 Информация о значении `HRESULT`.  
  
 `perrinfo`  
 Объект **IErrorInfo**.  
  
 **bool fAddRef\=false**  
 Дает конструктору указание вызвать метод AddRef на интерфейсе **IErrorInfo**, отличном от NULL.  Это обеспечивает правильный подсчет ссылок в распространенной ситуации, когда право владения интерфейсом передается в объект `_com_error`, например:  
  
```  
throw _com_error(hr, perrinfo);  
```  
  
 Если вы не хотите, чтобы код передавал право владения объекту `_com_error`, а метод `AddRef` необходим для смещения **выпуска** в деструкторе `_com_error`, создавайте объект следующим образом:  
  
```  
_com_error err(hr, perrinfo, true);  
```  
  
 `that`  
 Существующий объект `_com_error`.  
  
## Заметки  
 Первый конструктор создает новый объект, которому задается `HRESULT` и необязательный объект **IErrorInfo**.  Второй создает копию существующего объекта `_com_error`.  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Класс \_com\_error](../cpp/com-error-class.md)