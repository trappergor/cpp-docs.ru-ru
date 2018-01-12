---
title: "-SECTION (ПРОГРАММА EDITBIN) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /section
dev_langs: C++
helpviewer_keywords:
- -SECTION editbin option
- SECTION editbin option
- alignment characters in sections
- /SECTION editbin option
ms.assetid: 4680ab4e-c984-4251-8241-93440cad7615
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 91ffb9bd0645cab51e4140697c41e5b715380fe8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="section-editbin"></a>/SECTION (EDITBIN)
```  
/SECTION:name[=newname][,attributes][alignment]  
```  
  
## <a name="remarks"></a>Примечания  
 Этот параметр изменяет атрибуты секции, переопределяя атрибуты, которые были установлены при компиляции и компоновке объектных файлов для раздела.  
  
 После двоеточия ( **:** ), укажите *имя* раздела. Чтобы изменить имя раздела, выполните *имя* со знака равенства (=) и *newname* для раздела.  
  
 Задать или изменить раздел `attributes`, укажите запятую (**,**) за которыми следует один или несколько атрибутов символов. Чтобы инвертировать атрибут, укажите перед его символом восклицательный знак (!). Следующие знаки определяют атрибуты памяти:  
  
|Атрибут|Параметр|  
|---------------|-------------|  
|c|код|  
|d|Удаляемое|  
|й|исполняемый файл|  
|i|инициализированные данные|  
|k|кэшированные виртуальной памяти|  
|m|Удалить ссылку|  
|o|Информация о связи|  
|p|выгружаемый виртуальной памяти|  
|r|чтение|  
|s|общие|  
|u|неинициализированные данные|  
|w|запись|  
  
 Для управления *выравнивание*, укажите знак **A** следует один из следующих знаков, чтобы задать размер выравнивания в байтах, следующим образом:  
  
|Знак|Размер выравнивания в байтах|  
|---------------|-----------------------------|  
|1|1|  
|2|2|  
|4|4|  
|8|8|  
|p|16|  
|t|32|  
|s|64|  
|x|без выравнивания|  
  
 Укажите `attributes` и *выравнивание* символов в виде строки без пробелов. Символы не учитывается регистр.  
  
## <a name="see-also"></a>См. также  
 [Параметры EDITBIN](../../build/reference/editbin-options.md)