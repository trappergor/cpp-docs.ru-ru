---
title: Метод HString::Set | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::Set
dev_langs:
- C++
ms.assetid: c9b3d613-95c4-48b0-999d-f5baf0804faf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6eb2261ab973245c78ec8f5e0269663e5181a0ab
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42590045"
---
# <a name="hstringset-method"></a>Метод HString::Set

Задает значение текущего **HString** объекта с помощью указанной строки расширенных символов или **HString** параметра.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT Set(
          const wchar_t* str) throw();
HRESULT Set(
          const wchar_t* str,
          unsigned int len
           ) throw();
HRESULT Set(
          const HSTRING& hstr
           ) throw();
```

### <a name="parameters"></a>Параметры

*str*  
Строка расширенных символов.

*функция Len*  
Максимальная длина *str* параметр, который будет назначен текущий **HString** объекта.

*HSTR*  
Существующий **HString** объекта.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс HString](../windows/hstring-class.md)