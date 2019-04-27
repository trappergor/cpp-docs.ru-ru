---
title: raw_dispinterfaces
ms.date: 11/04/2016
f1_keywords:
- raw_dispinterfaces
helpviewer_keywords:
- raw_dispinterfaces attribute
ms.assetid: f762864d-29bf-445b-825a-ba7b29a95409
ms.openlocfilehash: ef8ed3992c77df0f1d551e923ddc90c2d1bb9b0b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179845"
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