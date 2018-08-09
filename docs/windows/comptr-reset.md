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
ms.openlocfilehash: 74f26f520be276de863c612718de8520bffc1219
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649709"
---
# <a name="comptrreset"></a>ComPtr::Reset
Освобождает все ссылки на указатель на интерфейс, который связан с данным **ComPtr**.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
unsigned long Reset();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Число освобожденных ссылок, если таковые имеются.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)