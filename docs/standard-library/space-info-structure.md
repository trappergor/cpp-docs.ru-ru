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
ms.openlocfilehash: 3506572586f0dc8edc3f9e97955e7612bcea46ae
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
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
[space](http://msdn.microsoft.com/en-us/7fce0b0e-523b-4598-b218-47245d0204ca)<br/>
[Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md)<br/>
