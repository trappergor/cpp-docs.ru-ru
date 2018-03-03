---
title: "-REBASE | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /rebase
dev_langs:
- C++
helpviewer_keywords:
- base addresses [C++]
- -REBASE editbin option
- REBASE editbin option
- DLLs [C++], linking
- executable files [C++], base address
- /REBASE editbin option [C++]
ms.assetid: 3f89d874-af5c-485b-974b-fd205f6e1a4b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 50bb10acda1175d2cca12e7e4aff6fc9e5bae73a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="rebase"></a>/REBASE
```  
/REBASE[:modifiers]  
```  
  
## <a name="remarks"></a>Примечания  
 Этот параметр задает базовые адреса для указанных файлов. EDITBIN назначает новые базовые адреса в непрерывном адресном пространстве в соответствии с размером каждого файла с округлением до ближайших 64 КБ. Дополнительные сведения о базовых адресов см. в разделе [базовый адрес](../../build/reference/base-base-address.md) (/ BASE) компоновщика.  
  
 Укажите исполняемые файлы и DLL-библиотеки в ее *файлы* аргумент в командной строке EDITBIN в порядке, в котором они будут основаны. При необходимости можно указать один или несколько *модификаторы*, разделяя их запятой (**,**):  
  
|Модификатор|Действие|  
|--------------|------------|  
|БАЗОВЫЙ**=***адрес*|Предоставляет начальный адрес для переназначения базовых адресов в файлы. Укажите *адрес* в десятичное или нотации языка. Если BASE не указан, по умолчанию, начиная с базового адреса используется 0x400000. Если используется, БАЗОВОГО СПИСКА должен быть задан, и *адрес* задает конец диапазона базовых адресов.|  
|BASEFILE|Создает файл с именем COFFBASE. TXT, — это текстовый файл в формат, ожидаемый ссылки/BASE параметр.|  
|ВНИЗ|Указывает EDITBIN переназначить базовые адреса вниз от конечного адреса. Файлы будут переданы в порядке, указанном с помощью первый файл, расположенный в наибольший возможный адрес ниже конец диапазона адресов. BASE должен использоваться с вниз для гарантировать достаточное адресное пространство для размещения файлов. Чтобы определить адресное пространство, требуемое для указанных файлов, запустите EDITBIN с параметром/REBASE файлов и добавьте 64 КБ отображается общий размер.|  
  
## <a name="see-also"></a>См. также  
 [Параметры EDITBIN](../../build/reference/editbin-options.md)