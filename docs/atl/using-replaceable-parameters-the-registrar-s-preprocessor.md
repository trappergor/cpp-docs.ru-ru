---
title: Использование заменяемых параметров (ATL регистратор)
ms.date: 11/04/2016
helpviewer_keywords:
- '%MODULE%'
ms.assetid: 0b376994-84a6-4967-8d97-8c01dfc94efe
ms.openlocfilehash: 2474db2de384baa9113ed39aef4d3d9c9048903d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329232"
---
# <a name="using-replaceable-parameters-the-registrar39s-preprocessor"></a>Использование заменяемых параметров (Регистратор&#39;препроцессор)

Заменяемые параметры позволяют клиенту Регистратора указывать данные о времени выполнения. Для этого Регистратор поддерживает карту замены, в которую он вводит значения, связанные со сменными параметрами в скрипте. Регистратор делает эти записи во время выполнения.

## <a name="using-module"></a><a name="_atl_using_.25.module.25"></a>Использование %MODULE%

[Мастер управления ATL](../atl/reference/atl-control-wizard.md) автоматически генерирует скрипт, который использует. `%MODULE%` ATL использует этот сменный параметр для фактического расположения DLL или EXE вашего сервера.

## <a name="concatenating-run-time-data-with-script-data"></a>Совмещение данных о run-time с данными сценария

Другим использованием препроцессора является совмещение данных о времени выполнения с данными скриптов. Например, предположим, что нужна запись, содержащая полный путь к модулю со строкой «приложенный`, 1`в конце. Во-первых, определить следующее расширение:

```
'MySampleKey' = s '%MODULE%, 1'
```

Затем, прежде чем вызвать один из методов обработки скриптов, перечисленных в [вызове скриптов,](../atl/invoking-scripts.md)добавьте замену на карте:

[!code-cpp[NVC_ATL_Utilities#113](../atl/codesnippet/cpp/using-replaceable-parameters-the-registrar-s-preprocessor_1.cpp)]

Во время разбора скрипта Регистратор `'%MODULE%, 1'` расширяется до `c:\mycode\mydll.dll, 1`.

> [!NOTE]
> В скрипте регистратора 4K является максимальным размером маркера. (Токен – это любой узнаваемый элемент в синтаксисе.) Это включает токены, которые были созданы или расширены препроцессором.

> [!NOTE]
> Чтобы заменить значения замены во время выполнения, удалите вызов в скрипте на [DECLARE_REGISTRY_RESOURCE](../atl/reference/registry-macros.md#declare_registry_resource) или [DECLARE_REGISTRY_RESOURCEID](../atl/reference/registry-macros.md#declare_registry_resourceid) макрос. Вместо этого замените `UpdateRegistry` его собственным методом, который вызывает [CAtlModule::UpdateRegistryFromResourceD](../atl/reference/catlmodule-class.md#updateregistryfromresourced) или [CAtlModule::UpdateRegistryFromResourceS](../atl/reference/catlmodule-class.md#updateregistryfromresources), и передать массив _ATL_REGMAP_ENTRY структур. Ваш массив _ATL_REGMAP_ENTRY должен иметь по крайней мере одну запись, которая установлена на «NULL»,NULL», и эта запись всегда должна быть последней записью. В противном случае при вызове будет сгенерирована `UpdateRegistryFromResource` ошибка нарушения доступа.

> [!NOTE]
> При создании проекта, который выводит исполняемый, ATL автоматически добавляет кавычки вокруг имени пути, созданного во время выполнения, с параметром скрипта регистратора **%MODULE%.** Если вы не хотите, чтобы имя пути включало кавычки, вместо этого используйте новый **параметр%MODULE_RAW%.**
>
> При создании проекта, который выводит DLL, ATL не будет добавлять кавычки в имя пути, если используется **%MODULE%** или **%MODULE_RAW%.**

## <a name="see-also"></a>См. также раздел

[Creating Registrar Scripts](../atl/creating-registrar-scripts.md)
