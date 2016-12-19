---
title: "Неустранимая ошибка NMAKE U1073 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1073"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1073"
ms.assetid: d46bf2dd-400a-4802-9db2-f832e1c97f02
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Неустранимая ошибка NMAKE U1073
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

не хватает сведений для построения "имя\_целевого\_объекта"  
  
 Указанный целевой объект не существует, и выполняемая команда или применяемое правило зависимости отсутствует.  
  
### Возможные способы устранения данной ошибки  
  
1.  Проверьте правильность написания имени целевого объекта.  
  
2.  Если *имя\_целевого\_объекта* является псевдоцелью, укажите его в качестве цели в другом блоке описания.  
  
3.  Если *имя\_целевого\_объекта* является макровызовом, убедитесь, что оно не разворачивается до пустой строки \(null\).