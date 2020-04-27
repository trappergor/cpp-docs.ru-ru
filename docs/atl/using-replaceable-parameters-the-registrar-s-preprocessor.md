---
title: Использование заменяемых параметров (регистратор ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- '%MODULE%'
ms.assetid: 0b376994-84a6-4967-8d97-8c01dfc94efe
ms.openlocfilehash: debbccea5836fa63282b62ff87573160069fb169
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168687"
---
# <a name="using-replaceable-parameters-the-registrar39s-preprocessor"></a>Использование заменяемых параметров (регистратор&#39;s препроцессор)

Заменяемые параметры позволяют клиенту регистратора указывать данные времени выполнения. Для этого Регистратор сохраняет карту замены, в которую он вводит значения, связанные с заменяемыми параметрами в скрипте. Регистратор делает эти записи во время выполнения.

## <a name="using-module"></a><a name="_atl_using_.25.module.25"></a>Использование% MODULE%

[Мастер элементов управления ATL](../atl/reference/atl-control-wizard.md) автоматически создает скрипт, использующий `%MODULE%`. ATL использует этот заменяемый параметр для фактического расположения библиотеки DLL или EXE сервера.

## <a name="concatenating-run-time-data-with-script-data"></a>Объединение данных времени выполнения с данными сценария

Еще один способ использования препроцессора — объединение данных времени выполнения с данными сценария. Например, предположим, что требуется запись, которая содержит полный путь к модулю со строкой "`, 1`", добавленной в конец. Сначала определите следующее расширение:

```rgs
'MySampleKey' = s '%MODULE%, 1'
```

Затем перед вызовом одного из методов обработки сценария, перечисленных в окне [вызов скриптов](../atl/invoking-scripts.md), добавьте замену на карту:

[!code-cpp[NVC_ATL_Utilities#113](../atl/codesnippet/cpp/using-replaceable-parameters-the-registrar-s-preprocessor_1.cpp)]

Во время синтаксического анализа сценария регистратор расширяется `'%MODULE%, 1'` до. `c:\mycode\mydll.dll, 1`

> [!NOTE]
> В скрипте регистратора 4 КБ — это максимальный размер маркера. (Маркер — это любой распознаваемый элемент в синтаксисе.) Сюда входят маркеры, созданные или развернутые препроцессором.

> [!NOTE]
> Чтобы заменить значения замены во время выполнения, удалите вызов в скрипте в [DECLARE_REGISTRY_RESOURCE](../atl/reference/registry-macros.md#declare_registry_resource) или [DECLARE_REGISTRY_RESOURCEID](../atl/reference/registry-macros.md#declare_registry_resourceid) макрос. Вместо этого замените его собственным `UpdateRegistry` методом, который вызывает [Катлмодуле:: упдатерегистрифромресаурцед](../atl/reference/catlmodule-class.md#updateregistryfromresourced) или [катлмодуле:: упдатерегистрифромресаурцес](../atl/reference/catlmodule-class.md#updateregistryfromresources), и передайте массив структур _ATL_REGMAP_ENTRY. Массив _ATL_REGMAP_ENTRY должен иметь по крайней мере одну запись, для которой задано значение {NULL, NULL}, и эта запись всегда должна быть последней записью. В противном случае при `UpdateRegistryFromResource` вызове будет сформирована ошибка нарушения прав доступа.

> [!NOTE]
> При построении проекта, который выводит исполняемый файл, ATL автоматически добавляет кавычки для имени пути, созданного во время выполнения, с помощью параметра скрипта **% module%** регистратора. Если имя пути не должно содержать кавычки, используйте вместо него новый параметр **% MODULE_RAW%** .
>
> При построении проекта, который выводит библиотеку DLL, ATL не будет добавлять кавычки к имени пути, если используется **% module%** или **% MODULE_RAW%** .

## <a name="see-also"></a>См. также

[Creating Registrar Scripts](../atl/creating-registrar-scripts.md)
