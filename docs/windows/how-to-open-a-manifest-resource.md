---
title: 'Как: Открытие ресурса манифеста (C++) | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- manifest resources [C++]
- resources [C++], opening
ms.assetid: bd6f9c47-2a1e-417d-9d2a-c1ad7d3b9635
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0825e34515a458d49b8353f3053654094d8b9526
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46407287"
---
# <a name="how-to-open-a-manifest-resource"></a>Практическое руководство. Открытие ресурса манифеста

Если вы откроете ресурс манифеста из [представления ресурсов](../windows/resource-view-window.md), этот ресурс откроется в двоичном формате. Чтобы просмотреть содержимое ресурса манифеста в более удобном формате, необходимо открыть ресурс из **обозревателе решений**.

### <a name="to-open-a-manifest-resource-in-the-text-editor"></a>Открытие ресурса манифеста в текстовом редакторе

1. Открыв проект в **обозревателе решений**, разверните **файлы ресурсов** папки.

2. Дважды щелкните файл с расширением MANIFEST.

   Ресурс манифеста откроется в **текстовый редактор**.

### <a name="to-open-a-manifest-resource-in-another-editor"></a>Открытие ресурса манифеста в другом редакторе

1. В **обозревателе решений**, щелкните правой кнопкой мыши файл с расширением MANIFEST и выберите **открыть с помощью...**  в контекстном меню.

2. В диалоговом окне **Открыть с помощью** выберите редактор, который вы хотите использовать, и нажмите кнопку **Открыть**.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*.

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Ресурсы манифеста](../windows/manifest-resources.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)<br/>
[Работа с файлами ресурсов](../windows/working-with-resource-files.md)