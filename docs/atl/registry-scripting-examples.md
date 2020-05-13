---
title: Примеры сценариев реестра
ms.date: 11/04/2016
helpviewer_keywords:
- scripting, examples
- registrar scripts [ATL]
- scripts, Registrar scripts
- registry, Registrar
ms.assetid: b6df80e1-e08b-40ee-9243-9b381b172460
ms.openlocfilehash: 0e225ce28309aa619fd9436d8f4b93e60544e86c
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168752"
---
# <a name="registry-scripting-examples"></a>Примеры сценариев реестра

В примерах сценариев в этом разделе показано, как добавить ключ в системный реестр, зарегистрировать сервер COM регистратора и указать несколько деревьев синтаксического анализа.

## <a name="add-a-key-to-hkey_current_user"></a>Добавление ключа в HKEY_CURRENT_USER

В следующем дереве синтаксического анализа показан простой скрипт, который добавляет один ключ в системный реестр. В частности, скрипт добавляет ключ, `MyVeryOwnKey`в. `HKEY_CURRENT_USER` Он также присваивает строковое значение `HowGoesIt` по умолчанию новому ключу:

```rgs
HKEY_CURRENT_USER
{
    'MyVeryOwnKey' = s 'HowGoesIt'
}
```

Этот скрипт можно легко расширить для определения нескольких подразделов следующим образом:

```rgs
HKCU
{
    'MyVeryOwnKey' = s 'HowGoesIt'
    {
        'HasASubkey'
        {
            'PrettyCool' = d '55'
            val 'ANameValue' = s 'WithANamedValue'
        }
    }
}
```

Теперь скрипт добавляет подраздел, `HasASubkey`в. `MyVeryOwnKey` `PrettyCool` Для этого подраздела добавляется подраздел (со значением по умолчанию `DWORD` 55) и `ANameValue` именованное значение (со строковым значением `WithANamedValue`).

## <a name="register-the-registrar-com-server"></a><a name="_atl_register_the_registrar_com_server"></a>Регистрация сервера COM регистратора

Следующий скрипт регистрирует сам COM-сервер регистратора.

```rgs
HKCR
{
    ATL.Registrar = s 'ATL Registrar Class'
    {
        CLSID = s '{44EC053A-400F-11D0-9DCD-00A0C90391D3}'
    }
    NoRemove CLSID
    {
        ForceRemove {44EC053A-400F-11D0-9DCD-00A0C90391D3} = s 'ATL Registrar Class'
        {
            ProgID = s 'ATL.Registrar'
            InprocServer32 = s '%MODULE%'
            {
                val ThreadingModel = s 'Apartment'
            }
        }
    }
}
```

Во время выполнения этот дерево анализа добавляет `ATL.Registrar` ключ в. `HKEY_CLASSES_ROOT` В этот новый раздел:

- Указывает `ATL Registrar Class` в качестве строкового значения по умолчанию для ключа.

- Добавляет `CLSID` в качестве подраздела.

- Указывает `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` для `CLSID`. (Это значение является идентификатором CLSID регистратора для использования `CoCreateInstance`с.)

Поскольку `CLSID` является общим, его не следует удалять в режиме отмены регистрации. Оператор `NoRemove CLSID`, делает это, указывая, что `CLSID` должен быть открыт в режиме Register и проигнорирован в режиме отмены регистрации.

`ForceRemove` Оператор предоставляет функцию обслуживания, удаляя ключ и все его подразделы перед повторной созданием ключа. Это может быть полезно, если имена подразделов изменились. В этом примере скрипта проверяет `ForceRemove` , существует ли `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` уже. Если это так, `ForceRemove`выполните следующие действия:

- Рекурсивно удаляются `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` и все его подразделы.

- Повторное создание `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`.

- Добавляет `ATL Registrar Class` в качестве строкового значения по `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`умолчанию для.

Дерево синтаксического анализа теперь добавляет два новых подраздела в `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`. Первый ключ, `ProgID`, возвращает строковое значение по умолчанию, которое является идентификатором ProgID. Второй ключ, `InprocServer32`, получает строковое значение `%MODULE%`по умолчанию, которое представляет собой значение препроцессора, описанное в разделе [Использование заменяемых параметров (препроцессор регистратора)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)этой статьи. `InprocServer32`также получает именованное значение `ThreadingModel`со строковым значением. `Apartment`

## <a name="specify-multiple-parse-trees"></a>Указание нескольких деревьев синтаксического анализа

Чтобы указать более одного дерева синтаксического анализа в скрипте, просто поместите одно дерево в конец другого. Например, следующий скрипт добавляет ключ `MyVeryOwnKey`в деревья синтаксического анализа для `HKEY_CLASSES_ROOT` и: `HKEY_CURRENT_USER`

```rgs
HKCR
{
    'MyVeryOwnKey' = s 'HowGoesIt'
}
HKEY_CURRENT_USER
{
    'MyVeryOwnKey' = s 'HowGoesIt'
}
```

> [!NOTE]
> В скрипте регистратора 4 КБ — это максимальный размер маркера. (Маркер — это любой распознаваемый элемент в синтаксисе.) В `HKCR`предыдущем примере `HKEY_CURRENT_USER`скрипта,, `'MyVeryOwnKey'`, и `'HowGoesIt'` являются маркерами.

## <a name="see-also"></a>См. также

[Creating Registrar Scripts](../atl/creating-registrar-scripts.md)
