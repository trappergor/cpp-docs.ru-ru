---
title: "Неустранимая ошибка компилятора ресурсов RC1015 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC1015
dev_langs:
- C++
helpviewer_keywords:
- RC1015
ms.assetid: 23f187e1-5538-40b5-9042-edd2888f55c2
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: c466abac9b74c2f33f81f4b2ba771ffaf728ad94
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="resource-compiler-fatal-error-rc1015"></a>Неустранимая ошибка компилятора ресурсов RC1015
не удается открыть включаемый файл «ИмяФайла»  
  
 Указанный включаемый файл не существует, не может быть открыт или не найден.  
  
 Убедитесь в том, что параметры среды являются допустимыми и путь к файлу указан верно. Обеспечить доступность для компилятора ресурсов недостаточно дескрипторов файлов. Если файл находится на сетевом диске, убедитесь, что имеются разрешения для открытия файла.  
  
 RC1015 может возникать, даже если включаемый файл существует в каталоге, указанном в качестве дополнительного каталога включения в свойствах конфигурации-> ресурсов-> странице общих свойств; Укажите полный путь к включаемому файлу.  
  
 Дополнительные сведения см. в статье базы знаний Q326987: RC1015 ошибки при использование ресурсов представление пути включаемых при слишком длинное.
