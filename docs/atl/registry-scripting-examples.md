---
title: Примеры скриптов реестра
ms.date: 11/04/2016
helpviewer_keywords:
- scripting, examples
- registrar scripts [ATL]
- scripts, Registrar scripts
- registry, Registrar
ms.assetid: b6df80e1-e08b-40ee-9243-9b381b172460
ms.openlocfilehash: dffdd111d33d6fbd845e1534cdef1d5c8e1749d2
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57262939"
---
# <a name="registry-scripting-examples"></a>Примеры скриптов реестра

Примеры скриптов в этом разделе показано, как добавить раздел в системный реестр, зарегистрируйте сервер COM регистратора и указания нескольких деревьях синтаксического анализа.

## <a name="add-a-key-to-hkeycurrentuser"></a>Добавление раздела HKEY_CURRENT_USER

Следующее дерево синтаксического анализа показан простой сценарий, который добавляет один ключ в системный реестр. В частности, он добавляет ключ `MyVeryOwnKey`, `HKEY_CURRENT_USER`. А также назначает строковое значение по умолчанию `HowGoesIt` к новому ключу:

```
HKEY_CURRENT_USER
{
    'MyVeryOwnKey' = s 'HowGoesIt'
}
```

Этот сценарий можно расширить легко определить несколько подразделов, следующим образом:

```
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

Теперь, сценарий добавляет подраздел, `HasASubkey`, `MyVeryOwnKey`. В этом подразделе, он добавляет Оба `PrettyCool` подраздел (значение по умолчанию `DWORD` значение 55) и `ANameValue` именованное значение (со значением строки `WithANamedValue`).

##  <a name="_atl_register_the_registrar_com_server"></a> Зарегистрируйте сервер COM регистратора

Следующий сценарий регистрирует сам сервер COM регистратора.

```
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

Во время выполнения, в данном дереве синтаксического анализа добавляет `ATL.Registrar` ключа `HKEY_CLASSES_ROOT`. Для этого нового ключа затем ИТ:

- Указывает `ATL Registrar Class` как строковое значение для ключа по умолчанию.

- Добавляет `CLSID` виде подраздела.

- Указывает `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` для `CLSID`. (Это значение равно регистратора CLSID для использования с `CoCreateInstance`.)

Поскольку `CLSID` является общим, его не следует удалять в режиме Unregister. Инструкция, `NoRemove CLSID`, достигается путем означает, что `CLSID` следует открыть в режиме Register и учитывается в режиме Unregister.

`ForceRemove` Инструкция предоставляет функции по обслуживанию, удалив ключ и все его подразделы перед повторным созданием ключа. Это может быть полезно в том случае, если были изменены имена подразделов. В этом примере сценария `ForceRemove` проверяет, если `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` уже существует. В этом случае `ForceRemove`:

- Рекурсивно удаляет `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` и все его подразделы.

- Повторно создает `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`.

- Добавляет `ATL Registrar Class` как строковое значение по умолчанию для `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`.

Дерево синтаксического анализа теперь добавляет два новых разделов для `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`. Первый ключ, `ProgID`, возвращает строковое значение по умолчанию, это идентификатор ProgID. Второй ключ `InprocServer32`, возвращает строковое значение по умолчанию, `%MODULE%`, то есть значение препроцессора, как описано в разделе [с помощью подстановочных параметров (препроцессор регистратора)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md), этой статьи. `InprocServer32` также возвращает значение именованного `ThreadingModel`, со значением строки `Apartment`.

## <a name="specify-multiple-parse-trees"></a>Укажите несколько деревьях синтаксического анализа

Чтобы указать более одного дерево синтаксического анализа в сценарий, просто поместите одно дерево в конце другой. Например, следующий сценарий добавляет ключ `MyVeryOwnKey`, чтобы деревьях синтаксического анализа для обоих `HKEY_CLASSES_ROOT` и `HKEY_CURRENT_USER`:

```
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
> В сценарии регистратора 4 КБ — максимальный размер маркера. (Маркер — это любой элемент, распознаваемый в синтаксисе.) В предыдущем примере сценария `HKCR`, `HKEY_CURRENT_USER`, `'MyVeryOwnKey'`, и `'HowGoesIt'` все маркеры.

## <a name="see-also"></a>См. также

[Создание скриптов регистратора](../atl/creating-registrar-scripts.md)
