---
title: Оператор __if_not_exists
ms.date: 11/04/2016
f1_keywords:
- __if_not_exists_cpp
helpviewer_keywords:
- __if_not_exists keyword [C++]
ms.assetid: a2f322d4-e96f-4a32-954e-4323d20c6e32
ms.openlocfilehash: 3e0eb550830a1689d440e3b471759a98f1eef0ca
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87187261"
---
# <a name="__if_not_exists-statement"></a>Оператор __if_not_exists

**`__if_not_exists`** Оператор проверяет, существует ли указанный идентификатор. Если идентификатор не существует, выполняется определенный блок операторов.

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
|*инструкции*|Одна или несколько инструкций для выполнения, если *идентификатор* не существует.|

## <a name="remarks"></a>Remarks

> [!CAUTION]
> Для достижения наиболее достоверных результатов используйте **`__if_not_exists`** инструкцию под следующими ограничениями.

- Примените **`__if_not_exists`** инструкцию только к простым типам, а не к шаблонам.

- Примените **`__if_not_exists`** инструкцию к идентификаторам как внутри, так и вне класса. Не применяйте **`__if_not_exists`** инструкцию к локальным переменным.

- Используйте **`__if_not_exists`** оператор только в теле функции. За пределами тела функции **`__if_not_exists`** инструкция может проверять только полностью определенные типы.

- При проверке перегруженных функций невозможно выполнить проверку определенной формы перегрузки.

Дополнение к **`__if_not_exists`** оператору является оператором [__if_exists](../cpp/if-exists-statement.md) .

## <a name="example"></a>Пример

Пример использования см **`__if_not_exists`** . в разделе [оператор __if_exists](../cpp/if-exists-statement.md).

## <a name="see-also"></a>См. также раздел

[Инструкции выбора](../cpp/selection-statements-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[__if_exists, инструкция](../cpp/if-exists-statement.md)
