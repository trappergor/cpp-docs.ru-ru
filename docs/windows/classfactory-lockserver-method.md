---
title: "Метод ClassFactory::LockServer | Microsoft Docs"
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
  - "module/Microsoft::WRL::ClassFactory::LockServer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LockServer - метод"
ms.assetid: 8d859815-956d-4f81-a5af-7cdee7e945de
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод ClassFactory::LockServer
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Увеличивает или уменьшает число базовых объектов, отслеживаемых текущим объектом ClassFactory.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
STDMETHOD(  
   LockServer  
)(BOOL fLock);  
```  
  
#### <a name="parameters"></a>Параметры  
 `fLock`  
Значение  `true` для увеличения числа отслеживаемых объектов. Значение `false` для уменьшения числа отслеживаемых объектов.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение E_FAIL.  
  
## <a name="remarks"></a>Примечания  
 ClassFactory отслеживает список объектов в базовом экземпляре класса [модуль](../windows/module-class.md) класса.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также раздел  
 [Класс ClassFactory](../windows/classfactory-class.md)