---
title: "Оператор Mutex::operator= | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Mutex::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator= - оператор"
ms.assetid: 9b0ee206-a930-4fea-8dc0-1f79839e9d13
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор Mutex::operator=
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Назначает (перемещается) указанный мьютекс объекта на текущий объект Mutex.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Mutex& operator=(  
   _Inout_ Mutex&& h  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `h`  
 Ссылка rvalue на объект Mutex.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Ссылка на текущий объект Mutex.  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе **семантику перемещения** раздел [декларатор ссылки Rvalue: & &](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers
 
 ## <a name="see-also"></a>См. также
 [Класс Mutex](Mutex%20Class1.md)