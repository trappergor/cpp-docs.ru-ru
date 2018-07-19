---
title: Структура once_flag | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 4275b99ada0dbfe1c974446d21862f7fa73aab38
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964500"
---
# <a name="onceflag-structure"></a>Структура once_flag

Представляет **структуры** , используемый с функцией шаблона [call_once](../standard-library/mutex-functions.md#call_once) чтобы убедиться, что инициализация кода вызывается только один раз, даже при наличии нескольких потоков выполнения.

## <a name="syntax"></a>Синтаксис

struct once_flag { constexpr once_flag() noexcept; once_flag(const once_flag&); once_flag& operator=(const once_flag&); };

## <a name="remarks"></a>Примечания

`once_flag` **Структуры** имеет только конструктор по умолчанию.

Объекты типа `once_flag` могут быть созданы, но их нельзя скопировать.

## <a name="requirements"></a>Требования

**Заголовок:** \<mutex >

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<mutex>](../standard-library/mutex.md)<br/>
