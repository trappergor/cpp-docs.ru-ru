---
title: Оператор __if_not_exists
ms.date: 11/04/2016
f1_keywords:
- __if_not_exists_cpp
helpviewer_keywords:
- __if_not_exists keyword [C++]
ms.assetid: a2f322d4-e96f-4a32-954e-4323d20c6e32
ms.openlocfilehash: 7372ac127a7b4dd5c05d58cfecca25f87690b0ae
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178195"
---
# <a name="__if_not_exists-statement"></a>Оператор __if_not_exists

Оператор **__if_not_exists** проверяет, существует ли указанный идентификатор. Если идентификатор не существует, выполняется определенный блок операторов.

## <a name="syntax"></a>Синтаксис

```
__if_not_exists ( identifier ) {
statements
};
```

#### <a name="parameters"></a>Параметры

|Параметр|Description|
|---------------|-----------------|
|*identifier*|Идентификатор, наличие которого требуется проверить.|
|*инструкции*|Одна или несколько инструкций для выполнения, если *идентификатор* не существует.|

## <a name="remarks"></a>Remarks

> [!CAUTION]
>  Для достижения наиболее достоверных результатов используйте инструкцию **__if_not_exists** в следующих ограничениях.

- Примените оператор **__if_not_exists** только к простым типам, а не к шаблонам.

- Примените оператор **__if_not_exists** к идентификаторам внутри или за пределами класса. Не применяйте оператор **__if_not_exists** к локальным переменным.

- Используйте оператор **__if_not_exists** только в теле функции. За пределами тела функции оператор **__if_not_exists** может проверять только полностью определенные типы.

- При проверке перегруженных функций невозможно выполнить проверку определенной формы перегрузки.

Дополнение к оператору **__if_not_exists** является оператором [__if_exists](../cpp/if-exists-statement.md) .

## <a name="example"></a>Пример

Пример использования **__if_not_exists**см. в разделе [__if_exists инструкция](../cpp/if-exists-statement.md).

## <a name="see-also"></a>См. также раздел

[Операторы выбора](../cpp/selection-statements-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Оператор __if_exists](../cpp/if-exists-statement.md)
