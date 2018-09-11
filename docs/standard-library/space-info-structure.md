---
title: Структура space_info | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- filesystem/std::tr2::sys::space_info
dev_langs:
- C++
ms.assetid: f2b35b42-06ff-45bd-8617-39a0f5358a54
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8a0f1eb9818356e7261125efaea69e275c3e29b8
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43684687"
---
# <a name="spaceinfo-structure"></a>Структура space_info

Содержит сведения о томе.

## <a name="syntax"></a>Синтаксис

```cpp
struct space_info   {
    uintmax_t capacity;
    uintmax_t free;
    uintmax_t available;
    };
```

## <a name="members"></a>Участники

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|`unsigned long long available`|Представляет число байтов, доступных для представления данных в томе.|
|`unsigned long long capacity`|Представляет общее число байтов, которое может представлять том.|
|`unsigned long long free`|Представляет число байтов, не используемых для представления данных в томе.|

## <a name="requirements"></a>Требования

**Заголовок:** \<filesystem >

**Пространство имен:** std::experimental::filesystem

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<filesystem>](../standard-library/filesystem.md)<br/>
[Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md)<br/>
