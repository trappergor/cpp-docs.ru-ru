---
title: Структура once_flag
ms.date: 09/17/2018
f1_keywords:
- mutex/std::once_flag
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
ms.openlocfilehash: 004a5545e2eccab83b0846e2ae30b88c8431c99d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62371442"
---
# <a name="onceflag-structure"></a>Структура once_flag

Представляет **структуры** , используемый с функцией шаблона [call_once](../standard-library/mutex-functions.md#call_once) чтобы убедиться, что инициализация кода вызывается только один раз, даже при наличии нескольких потоков выполнения.

## <a name="syntax"></a>Синтаксис

struct once_flag { constexpr once_flag() noexcept; };

## <a name="remarks"></a>Примечания

`once_flag` **Структуры** имеет только конструктор по умолчанию.

Объекты типа `once_flag` могут быть созданы, но их нельзя скопировать.

## <a name="requirements"></a>Требования

**Заголовок:** \<mutex >

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<mutex>](../standard-library/mutex.md)<br/>
