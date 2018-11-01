---
title: raw_dispinterfaces
ms.date: 11/04/2016
f1_keywords:
- raw_dispinterfaces
helpviewer_keywords:
- raw_dispinterfaces attribute
ms.assetid: f762864d-29bf-445b-825a-ba7b29a95409
ms.openlocfilehash: 8a6c335c7afe2cc56613f06abf5c181f05f6bfec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50585397"
---
# <a name="rawdispinterfaces"></a>raw_dispinterfaces
**Конкретных C++**

Указывает компилятору сгенерировать низкоуровневые функции оболочки для методов disp-интерфейса и свойства, которые вызывают `IDispatch::Invoke` и возвращают код ошибки HRESULT.

## <a name="syntax"></a>Синтаксис

```
raw_dispinterfaces
```

## <a name="remarks"></a>Примечания

Если этот атрибут не указан, создаются только высокоуровневые оболочки, которые в случае сбоя вызывают исключения C++.

**КОНЕЦ конкретных C++**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[директива #import](../preprocessor/hash-import-directive-cpp.md)