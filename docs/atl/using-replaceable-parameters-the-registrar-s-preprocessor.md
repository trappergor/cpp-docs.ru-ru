---
title: Использование подстановочных параметров (регистратор ATL)
ms.date: 11/04/2016
f1_keywords:
- AddReplacement
- ClearReplacements
helpviewer_keywords:
- '%MODULE%'
ms.assetid: 0b376994-84a6-4967-8d97-8c01dfc94efe
ms.openlocfilehash: c820307ecb0e7fbfe5cce7cd579ff46eb1f3a0f0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50588192"
---
# <a name="using-replaceable-parameters-the-registrar39s-preprocessor"></a>Использование подстановочных параметров (регистратор&#39;препроцессор s)

Подстановочные параметры позволяют указать данные времени выполнения клиент регистратора. Чтобы сделать это, регистратор хранит карту замены, в которую он входит в значения, связанные с подстановочные параметры в скрипте. Регистратор делает эти записи во время выполнения.

##  <a name="_atl_using_.25.module.25"></a> С помощью МОДУЛЯ %

[Мастер элементов управления ATL](../atl/reference/atl-control-wizard.md) автоматически формирует скрипт, который использует `%MODULE%`. ATL использует этот параметр можно заменить фактическое расположение библиотеки DLL или EXE-файла на сервере.

## <a name="concatenating-run-time-data-with-script-data"></a>Объединение данных во время выполнения с помощью данных сценария

Другой препроцессор используется для объединения данных во время выполнения с помощью данных сценария. Предположим, например, запись необходима, содержащий полный путь к модулю со строкой "`, 1`" в конце. Во-первых определите следующие расширения:

```
'MySampleKey' = s '%MODULE%, 1'
```

Затем, прежде чем вызвать один из скриптов, перечисленные в методы обработки [сценариев вызова](../atl/invoking-scripts.md), добавление на карту замены:

[!code-cpp[NVC_ATL_Utilities#113](../atl/codesnippet/cpp/using-replaceable-parameters-the-registrar-s-preprocessor_1.cpp)]

При анализе скрипта регистратора расширяет `'%MODULE%, 1'` для `c:\mycode\mydll.dll, 1`.

> [!NOTE]
>  В сценарии регистратора 4 КБ — максимальный размер маркера. (Маркер — это любой элемент, распознаваемый в синтаксисе.) Сюда входят маркеры, которые были созданы или развернут препроцессором.

> [!NOTE]
>  Для замены значений для замены во время выполнения, удалите вызов в сценарии для [DECLARE_REGISTRY_RESOURCE](../atl/reference/registry-macros.md#declare_registry_resource) или [DECLARE_REGISTRY_RESOURCEID](../atl/reference/registry-macros.md#declare_registry_resourceid) макрос. Вместо этого, замените его собственным `UpdateRegistry` метод, который вызывает [CAtlModule::UpdateRegistryFromResourceD](../atl/reference/catlmodule-class.md#updateregistryfromresourced) или [CAtlModule::UpdateRegistryFromResourceS](../atl/reference/catlmodule-class.md#updateregistryfromresources)и передайте массив _ATL_REGMAP_ ЭЛЕМЕНТ структуры. Массив _ATL_REGMAP_ENTRY должен иметь по крайней мере одна запись, которой присваивается {NULL, NULL}, и эта запись всегда должен быть последней операции. В противном случае будет ошибка нарушения доступа, формируемое, когда `UpdateRegistryFromResource` вызывается.

> [!NOTE]
>  При построении проекта, который выводит исполняемый файл ATL автоматически добавляет кавычки вокруг имени пути, созданному во время выполнения с **модуль %** параметр скрипта регистратора. Если не требуется имя пути в кавычки, используйте новый **% MODULE_RAW %** параметра вместо этого.
>
>  При построении проекта, который выводит библиотеку DLL, ATL не будет добавлять кавычки в имени пути Если **модуль %** или **% MODULE_RAW %** используется.

## <a name="see-also"></a>См. также

[Создание скриптов регистратора](../atl/creating-registrar-scripts.md)

