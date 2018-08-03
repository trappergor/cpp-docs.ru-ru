---
title: ComPtr::Reset | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: aa6a46f7-f56b-4fd5-add0-7cea55f7abda
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6edbe333ddb634d8657712695250ec627a171780
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461088"
---
# <a name="comptrreset"></a>ComPtr::Reset
Освобождает все ссылки на указатель на интерфейс, который связан с данным **ComPtr**.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
unsigned long Reset();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Число освобожденных ссылок, если таковые имеются.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)