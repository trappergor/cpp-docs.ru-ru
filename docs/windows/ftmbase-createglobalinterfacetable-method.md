---
title: "Метод FtmBase::CreateGlobalInterfaceTable | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ftm/Microsoft::WRL::FtmBase::CreateGlobalInterfaceTable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateGlobalInterfaceTable - метод"
ms.assetid: bb82a0c5-22b9-4844-9204-7922033d8b07
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Метод FtmBase::CreateGlobalInterfaceTable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает глобальную таблицу интерфейсов \(GIT\).  
  
## Синтаксис  
  
```  
static HRESULT CreateGlobalInterfaceTable(  
   __out IGlobalInterfaceTable **git  
);  
```  
  
#### Параметры  
 `git`  
 Когда эта операция будет завершена, указатель на общую таблицу интерфейса.  
  
## Возвращаемое значение  
 Значение S\_ОК в случае успеха; в противном случае — значение HRESULT, указывающее на ошибку.  
  
## Примечания  
 Дополнительные сведения см. в разделе «IGlobalInterfaceTable» в подразделе «Интерфейсы модели COM» раздела «Справка по модели COM» в библиотеке MSDN.  
  
## Требования  
 **Заголовок:** ftm.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс FtmBase](../windows/ftmbase-class.md)