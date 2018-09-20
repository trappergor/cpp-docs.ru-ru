---
title: Конструктор CriticalSection::CriticalSection | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::CriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CriticalSection, constructor
ms.assetid: 930b89be-4d74-46bd-8879-5dd4d15bcbd0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b992f4ad781105a8795a7bf95ff8b831ab961275
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400683"
---
# <a name="criticalsectioncriticalsection-constructor"></a>Конструктор CriticalSection::CriticalSection

Инициализирует объект синхронизации, аналогичны объект mutex, но может использоваться только потоки одного процесса.

## <a name="syntax"></a>Синтаксис

```cpp
explicit CriticalSection(
   ULONG spincount = 0
);
```

### <a name="parameters"></a>Параметры

*spinCount*<br/>
Счетчик прокруток для объекта критической секции. Значение по умолчанию — 0.

## <a name="remarks"></a>Примечания

Дополнительные сведения о критических секциях и прокруток см. в разделе `InitializeCriticalSectionAndSpinCount` работать в **синхронизации** раздел документации по Windows API.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс CriticalSection](../windows/criticalsection-class.md)