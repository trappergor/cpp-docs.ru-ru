---
title: Структура once_flag
ms.date: 09/17/2018
f1_keywords:
- mutex/std::once_flag
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
ms.openlocfilehash: fb85bd48f9b1ac10ec2fefbc6738aae777f67bcf
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455197"
---
# <a name="onceflag-structure"></a>Структура once_flag

Представляет **структуру** , которая используется с функцией-шаблоном [call_once](../standard-library/mutex-functions.md#call_once) для того, чтобы код инициализации вызывался только один раз, даже при наличии нескольких потоков выполнения.

## <a name="syntax"></a>Синтаксис

struct once_flag { constexpr once_flag() noexcept; };

## <a name="remarks"></a>Примечания

Структура имеет только конструктор по умолчанию.  `once_flag`

Объекты типа `once_flag` могут быть созданы, но их нельзя скопировать.

## <a name="requirements"></a>Требования

**Заголовок:** \<> мьютекса

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)
