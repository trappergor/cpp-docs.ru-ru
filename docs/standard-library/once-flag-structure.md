---
title: Структура once_flag | Документы Майкрософт
ms.custom: ''
ms.date: 09/17/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- mutex/std::once_flag
dev_langs:
- C++
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 67cfbe06461598fbd04e124629399baa63fdd5d9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46104339"
---
# <a name="onceflag-structure"></a>Структура once_flag

Представляет **структуры** , используемый с функцией шаблона [call_once](../standard-library/mutex-functions.md#call_once) чтобы убедиться, что инициализация кода вызывается только один раз, даже при наличии нескольких потоков выполнения.

## <a name="syntax"></a>Синтаксис

Структура once_flag {constexpr once_flag() noexcept;};

## <a name="remarks"></a>Примечания

`once_flag` **Структуры** имеет только конструктор по умолчанию.

Объекты типа `once_flag` могут быть созданы, но их нельзя скопировать.

## <a name="requirements"></a>Требования

**Заголовок:** \<mutex >

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<mutex>](../standard-library/mutex.md)<br/>
