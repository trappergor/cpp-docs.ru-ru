---
title: raw_dispinterfaces, атрибут импорта
ms.date: 08/29/2019
f1_keywords:
- raw_dispinterfaces
helpviewer_keywords:
- raw_dispinterfaces attribute
ms.assetid: f762864d-29bf-445b-825a-ba7b29a95409
ms.openlocfilehash: 73c58b72b27de8dcf96e8ab9464d0fb6bce12b66
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216226"
---
# <a name="raw_dispinterfaces-import-attribute"></a>raw_dispinterfaces, атрибут импорта

**C++Зависящ**

Указывает компилятору создавать низкоуровневые функции оболочки для методов disp-интерфейсов, а также для свойств, `IDispatch::Invoke` которые вызывают и возвращают код ошибки HRESULT.

## <a name="syntax"></a>Синтаксис

> **#import** *Библиотека типов* **raw_dispinterfaces**

## <a name="remarks"></a>Примечания

Если этот атрибут не указан, создаются только высокоуровневые оболочки, которые создают C++ исключения при сбое.

**КОНЕЦ C++ конкретного**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)\
[Директива #import](../preprocessor/hash-import-directive-cpp.md)
