---
title: "Функция RaiseException | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "internal/Microsoft::WRL::Details::RaiseException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RaiseException - функция"
ms.assetid: f9c74f6d-112a-4d2e-900f-622f795d5dbf
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Функция RaiseException
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
inline void __declspec(noreturn)  
   RaiseException(  
      HRESULT hr,   
      DWORD dwExceptionFlags = EXCEPTION_NONCONTINUABLE);  
```  
  
#### Параметры  
 `hr`  
 Вызывается код исключения в исключении; то есть HRESULT неудачно завершенной операции.  
  
 `dwExceptionFlags`  
 Флажок, который указывает продолжаемое исключение \(значение флажка равно нулю\) или непродолжаемое исключение \(ненулевое значение флажка\).  По умолчанию исключение является непродолжаемым.  
  
## Примечания  
 Создает исключение в вызывающем потоке.  
  
 Для получения дополнительных сведений см. функцию **RaiseException** Windows.  
  
## Требования  
 **Заголовок:** internal.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)