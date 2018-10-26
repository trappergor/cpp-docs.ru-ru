---
title: raw_dispinterfaces | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- raw_dispinterfaces
dev_langs:
- C++
helpviewer_keywords:
- raw_dispinterfaces attribute
ms.assetid: f762864d-29bf-445b-825a-ba7b29a95409
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b89c1f549168a762b5ae095c4eacf5ddb1b4d053
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50062357"
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