---
title: Структура once_flag
ms.date: 09/17/2018
f1_keywords:
- mutex/std::once_flag
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
ms.openlocfilehash: 004a5545e2eccab83b0846e2ae30b88c8431c99d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50481975"
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
