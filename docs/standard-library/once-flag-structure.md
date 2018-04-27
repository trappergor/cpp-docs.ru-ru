---
title: Структура once_flag | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- mutex/std::once_flag
dev_langs:
- C++
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 249207d8723318c1a11760c512f3b88f13c97266
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="onceflag-structure"></a>Структура once_flag

Представляет объект `struct`, который используется с функцией шаблона [call_once](../standard-library/mutex-functions.md#call_once) для обеспечения однократного вызова кода инициализации даже при наличии нескольких потоков выполнения.

## <a name="syntax"></a>Синтаксис

struct once_flag { constexpr once_flag() noexcept; once_flag(const once_flag&); once_flag& operator=(const once_flag&); };

## <a name="remarks"></a>Примечания

`once_flag` `struct` Имеет конструктор по умолчанию.

Объекты типа `once_flag` могут быть созданы, но их нельзя скопировать.

## <a name="requirements"></a>Требования

**Заголовок:** \<мьютекс >

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<mutex>](../standard-library/mutex.md)<br/>
