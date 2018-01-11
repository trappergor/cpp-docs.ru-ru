---
title: "Добавление ресурса-диалоговое окно | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.insertresource
dev_langs: C++
helpviewer_keywords:
- resources [Visual Studio], adding
- Add Resource dialog box
ms.assetid: e9fb6967-738f-47e8-ab58-728cf35b3af0
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fde90f5d7c7822155e36b77c74cd80cdf56b10d2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="add-resource-dialog-box"></a>Добавление ресурса - диалоговое окно
Это диалоговое окно предназначено для добавления ресурсов в проект классического приложения Windows C++.  
  
> [!NOTE]
>  Эти сведения не относятся к ресурсам в приложениях для Магазина Windows. Дополнительные сведения об этом см. в разделе [определение ресурсов приложения](http://msdn.microsoft.com/en-us/476ea844-632c-4467-9ce3-966be1350dd4).  
  
 **Тип ресурса**  
 Указывает тип ресурса, который требуется создать.  
  
 Можно развернуть категории ресурсов курсора и диалогового окна, чтобы просмотреть дополнительные ресурсы. Эти ресурсы находятся в ...\Microsoft Visual Studio `version`\VC\VCResourceTemplates\\< LCID\>\mfc.rct. При добавлении RCT-файлы, необходимо поместить их в этот каталог или необходимо указать [путь включения](../windows/how-to-specify-include-directories-for-resources.md) для них. В этом случае ресурсы в этих файлах появятся на втором уровне в соответствующей категории. Количество добавляемых RCT-файлов не ограничено.  
  
 Ресурсы, показанные на верхнем уровне в элементе управления "дерево", — это ресурсы по умолчанию, предоставляемые Visual Studio.  
  
 **Создать**  
 Создает ресурс на основе типа, выбранного в **тип ресурса** поле. Ресурс открывается в соответствующем редакторе. Например, при создании ресурса диалогового окна он открывается в [редактор диалоговых окон](../windows/dialog-editor.md).  
  
 **Import**  
 Открывает **импорта** диалоговое окно «», в которой можно перейти к ресурсу вам нужно импортировать в текущий проект. Можно импортировать растровое изображение, значок, курсор, файл ресурсов HTML, звуковой файл ресурсов (WAV) или настраиваемый файл ресурсов.  
  
 **Пользовательский**  
 Открывает [Создание настраиваемого ресурса-диалоговое окно](../windows/new-custom-resource-dialog-box.md) , в котором можно создать настраиваемый ресурс. Настраиваемые ресурсы можно редактировать только в двоичном редакторе.  
  
## <a name="requirements"></a>Требования  
 Нет  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Создание ресурса](../windows/how-to-create-a-resource.md)