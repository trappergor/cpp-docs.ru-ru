---
title: "Метод ComPtr::ReleaseAndGetAddressOf | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf
dev_langs: C++
helpviewer_keywords: ReleaseAndGetAddressOf method
ms.assetid: 3751dcb4-d50e-432c-89e4-e736be34d434
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b6711cc93071c1e260a5d216a6ad21add9c00540
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="comptrreleaseandgetaddressof-method"></a>Метод ComPtr::ReleaseAndGetAddressOf
Освобождает интерфейс, связанный с данным объектом ComPtr, а затем извлекает адрес данных-члена [ptr_](../windows/comptr-ptr-data-member.md) , который содержит указатель на освобожденный интерфейс.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
T** ReleaseAndGetAddressOf();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Адрес [ptr_](../windows/comptr-ptr-data-member.md) элемента данных этого объекта ComPtr.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)   
 [Элемент данных ComPtr::ptr_](../windows/comptr-ptr-data-member.md)