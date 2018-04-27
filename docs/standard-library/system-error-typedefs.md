---
title: Определения типов &lt;system_error&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- system_error/std::generic_errno
ms.assetid: 28cf9f7d-9c28-4baa-a297-67c8260b07fb
caps.latest.revision: 11
manager: ghogen
ms.openlocfilehash: 701df57adb0576160f5aade9fd26220c852150ac
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="ltsystemerrorgt-typedefs"></a>Определения типов &lt;system_error&gt;

||
|-|
|[generic_errno](#generic_errno)|

## <a name="generic_errno"></a>  generic_errno

Тип, который представляет перечисление, предоставляющее символьные имена для всех макросов с ошибками в коде, определяемых Posix в `<errno.h>`.

```cpp
typedef errc generic_error;
```

### <a name="remarks"></a>Примечания

Тип является синонимом [errc](../standard-library/system-error-enums.md#errc).

## <a name="see-also"></a>См. также

[<system_error>](../standard-library/system-error.md)<br/>
