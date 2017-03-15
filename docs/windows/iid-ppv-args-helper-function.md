---
title: "Функция IID_PPV_ARGS_Helper | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/IID_PPV_ARGS_Helper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IID_PPV_ARGS_Helper - функция"
ms.assetid: afee9b23-8df1-4575-903f-e9ba748418f0
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Функция IID_PPV_ARGS_Helper
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Проверяет, что тип заданного аргумента является производным от интерфейса `IUnknown`.  
  
> [!IMPORTANT]
>  Данная специализация шаблона поддерживает инфраструктуру WRL и не предназначена для использования непосредственно из кода.  Взамен рекомендуется использовать [IID\_PPV\_ARGS](http://msdn.microsoft.com/library/windows/desktop/ee330727.aspx).  
  
## Синтаксис  
  
```  
template<  
   typename T  
>  
void** IID_PPV_ARGS_Helper(  
   _Inout_ Microsoft::WRL::Details::ComPtrRef<T> pp  
);  
```  
  
#### Параметры  
 `T`  
 Тип аргумента `pp`  
  
 `pp`  
 Двойной косвенный указатель.  
  
## Возвращаемое значение  
 Аргумент `pp` приводит указатель на указатель к `void`.  
  
## Примечания  
 Ошибка времени компиляции создается, если параметр `T` шаблона не является производным от `IUnknown`.  
  
## Требования  
 **Заголовок:** client.h  
  
## См. также  
 [Reference \(Windows Runtime Library\)](http://msdn.microsoft.com/ru-ru/00000000-0000-0000-0000-000000000000)