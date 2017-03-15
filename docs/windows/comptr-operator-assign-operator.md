---
title: "Оператор ComPtr::operator= | Microsoft Docs"
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
  - "client/Microsoft::WRL::ComPtr::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator= - оператор"
ms.assetid: 1a0c2752-f7d8-4819-9443-07b88b69ef02
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор ComPtr::operator=
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Присваивает значение текущему ComPtr.  
  
## Синтаксис  
  
```  
WRL_NOTHROW ComPtr& operator=(  
   decltype(__nullptr)  
);  
WRL_NOTHROW ComPtr& operator=(  
   _In_opt_ T *other  
);  
template <  
   typename U  
>  
WRL_NOTHROW ComPtr& operator=(  
   _In_opt_ U *other  
);  
WRL_NOTHROW ComPtr& operator=(  
   const ComPtr &other  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr& operator=(  
   const ComPtr<U>& other  
);  
WRL_NOTHROW ComPtr& operator=(  
   _Inout_ ComPtr &&other  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr& operator=(  
   _Inout_ ComPtr<U>&& other  
);  
```  
  
#### Параметры  
 `U`  
 Класс.  
  
 `other`  
 Указатель, ссылка или rvalue ссылаются на тип или другой ComPtr.  
  
## Возвращаемое значение  
 Ссылка на текущий ComPtr.  
  
## Примечания  
 Первая версия этого оператора присваивает пустое значение текущему ComPtr.  
  
 Во второй версии, если присваиваемый указатель интерфейса не совпадает с текущим указателем интерфейса ComPtr, второй указатель интерфейса присваивается текущему ComPtr.  
  
 В третьей версии присваиваемый указатель интерфейса присваивается текущему ComPtr.  
  
 В четвертой версии, если указатель интерфейса присваиваемого значения не совпадает с текущим указателем интерфейса ComPtr, второй указатель интерфейса присваивается текущему ComPtr.  
  
 Пятая версия является оператором копирования; ссылка на ComPtr присваивается текущему ComPtr.  
  
 Шестая версия является оператором копирования, использующим семантику перемещения; rvalue ссылается на ComPtr, если любой тип приводится статически, а затем присваивается текущему ComPtr.  
  
 Седьмая версия является оператором копирования, использующим семантику перемещения; rvalue ссылается на ComPtr типа `U`, который приводится статически, а затем присваивается текущему ComPtr.  
  
## Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс ComPtr](../windows/comptr-class.md)