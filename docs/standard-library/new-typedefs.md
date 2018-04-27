---
title: Определения типов &lt;new&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- new/std::new_handler
ms.assetid: aef01de1-06b5-4b6c-aebc-2c9f423d7e47
caps.latest.revision: 7
manager: ghogen
ms.openlocfilehash: 53a13168986171d3240cc15e405fc08b3db07e96
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="ltnewgt-typedefs"></a>Определения типов &lt;new&gt;

||
|-|
|[new_handler](#new_handler)|

## <a name="new_handler"></a>  new_handler

Тип указывает на функцию, подходящую для использования в качестве нового обработчика.

```cpp
typedef void (*new_handler)();
```

### <a name="remarks"></a>Примечания

Этот тип функции обработчика вызывается **operator new** или `operator new[]`, если они не могут удовлетворить запрос на дополнительное хранилище.

### <a name="example"></a>Пример

См. [set_new_handler](../standard-library/new-functions.md#set_new_handler) с примером использования `new_handler` в качестве как возвращаемого значения.

## <a name="see-also"></a>См. также

[\<new>](../standard-library/new.md)<br/>
