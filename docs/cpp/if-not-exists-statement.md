---
title: Оператор __if_not_exists
ms.date: 11/04/2016
f1_keywords:
- __if_not_exists_cpp
helpviewer_keywords:
- __if_not_exists keyword [C++]
ms.assetid: a2f322d4-e96f-4a32-954e-4323d20c6e32
ms.openlocfilehash: 845597460cdc0ce83adcbba1f47a78c83735cbf9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62183639"
---
# <a name="ifnotexists-statement"></a>Оператор __if_not_exists

**__If_not_exists** инструкции проверяет, является ли указанный идентификатор существует. Если идентификатор не существует, выполняется определенный блок операторов.

## <a name="syntax"></a>Синтаксис

```
__if_not_exists ( identifier ) {
statements
};
```

#### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*identifier*|Идентификатор, наличие которого требуется проверить.|
|*Инструкции*|Один или несколько операторов для выполнения, если *идентификатор* не существует.|

## <a name="remarks"></a>Примечания

> [!CAUTION]
>  Для достижения самых надежных результатов используйте **__if_not_exists** инструкции с учетом следующих ограничений.

- Применить **__if_not_exists** инструкцию, чтобы только простые типы, не шаблоны.

- Применить **__if_not_exists** инструкции к идентификаторам как внутри, так и вне класса. Не устанавливайте **__if_not_exists** инструкции для локальных переменных.

- Используйте **__if_not_exists** инструкции только в теле функции. За пределами тела функции **__if_not_exists** инструкция может проверять только полностью определенные типы.

- При проверке перегруженных функций невозможно выполнить проверку определенной формы перегрузки.

Дополнением к **__if_not_exists** инструкция является [__if_exists](../cpp/if-exists-statement.md) инструкции.

## <a name="example"></a>Пример

Пример использования **__if_not_exists**, см. в разделе [__if_exists инструкции](../cpp/if-exists-statement.md).

## <a name="see-also"></a>См. также

[Операторы выбора](../cpp/selection-statements-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Оператор __if_exists](../cpp/if-exists-statement.md)