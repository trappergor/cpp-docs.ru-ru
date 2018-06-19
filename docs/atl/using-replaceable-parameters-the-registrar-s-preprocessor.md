---
title: Использование подстановочных параметров (регистратор ATL) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- AddReplacement
- ClearReplacements
dev_langs:
- C++
helpviewer_keywords:
- '%MODULE%'
ms.assetid: 0b376994-84a6-4967-8d97-8c01dfc94efe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 91deabfd14d89c4a26384a14445fc51edbb3ac94
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362288"
---
# <a name="using-replaceable-parameters-the-registrar39s-preprocessor"></a>Использование подстановочных параметров (регистратор&#39;препроцессор s)
Подстановочные параметры позволяют клиенту регистратора указания данных во время выполнения. Чтобы сделать это, регистратор поддерживает замены карты, в которую он входит в значения, связанные с подстановочные параметры в скрипте. Регистратор делает эти записи во время выполнения.  
  
##  <a name="_atl_using_.25.module.25"></a> С помощью МОДУЛЯ %  
 [Мастер элементов управления ATL](../atl/reference/atl-control-wizard.md) автоматически формирует скрипт, который использует `%MODULE%`. ATL использует этот подставляемый фактическое расположение библиотеки DLL или EXE-файла на сервере.  
  
## <a name="concatenating-run-time-data-with-script-data"></a>Объединение данных во время выполнения с помощью данных сценария  
 Другой препроцессор используется для объединения данных во время выполнения с помощью данных сценария. Предположим, что запись необходима, содержащий полный путь к модулю со строкой «`, 1`» в конце. Во-первых определите следующие расширения:  
  
```  
'MySampleKey' = s '%MODULE%, 1'  
```  
  
 Затем перед вызовом одного из сценария обработки методов, перечисленных в [сценариев вызова](../atl/invoking-scripts.md), добавить в схему замены:  
  
 [!code-cpp[NVC_ATL_Utilities#113](../atl/codesnippet/cpp/using-replaceable-parameters-the-registrar-s-preprocessor_1.cpp)]  
  
 При анализе скрипта регистратора расширяет `'%MODULE%, 1'` для `c:\mycode\mydll.dll, 1`.  
  
> [!NOTE]
>  В скрипте регистратора 4 КБ — максимальный размер маркера. (Маркер представляет любой элемент, распознаваемые в синтаксисе). Это включает в себя токены, которые были созданы или развернут препроцессором.  
  
> [!NOTE]
>  Для замены значений для замены во время выполнения, удалите вызов в скрипте, чтобы [DECLARE_REGISTRY_RESOURCE](../atl/reference/registry-macros.md#declare_registry_resource) или [DECLARE_REGISTRY_RESOURCEID](../atl/reference/registry-macros.md#declare_registry_resourceid) макрос. Вместо этого, замените его собственного `UpdateRegistry` метод, который вызывает [CAtlModule::UpdateRegistryFromResourceD](../atl/reference/catlmodule-class.md#updateregistryfromresourced) или [CAtlModule::UpdateRegistryFromResourceS](../atl/reference/catlmodule-class.md#updateregistryfromresources)и передать массив из **_ATL_REGMAP_ENTRY** структуры. Ваш массив **_ATL_REGMAP_ENTRY** необходимо иметь по крайней мере одну запись, которой присваивается {**NULL**,**NULL**}, и этот элемент всегда должен быть последней операции. В противном случае будет ошибка нарушения доступа, сформированные при **UpdateRegistryFromResource** вызывается.  
  
> [!NOTE]
>  При построении проекта с выходными исполняемый файл, ATL автоматически добавляет кавычки вокруг имени пути, созданному во время выполнения с **модуль %** параметр скрипта регистратора. Если не требуется имя пути, чтобы заключить в кавычки, использовать новую **% MODULE_RAW %** параметра вместо этого.  
>   
>  При построении проекта с выходными библиотеки DLL, ATL не добавления кавычек в имени пути, если **модуль %** или **% MODULE_RAW %** используется.  
  
## <a name="see-also"></a>См. также  
 [Создание скриптов регистратора](../atl/creating-registrar-scripts.md)

