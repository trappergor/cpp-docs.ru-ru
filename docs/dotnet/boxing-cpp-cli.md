---
title: "Упаковка-преобразование (C + +/ CLI) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: f4ee27a8-6a34-432d-b9ec-39285d513b23
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e49c6f82099e6d7dbcfc47079d19228d7a91dc05
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="boxing-ccli"></a>упаковка-преобразование (C++/CLI)
Упаковка-преобразование — это процесс преобразования типа значения в тип `object` или любой другой тип интерфейса, который реализуется типом значения. Когда тип значения упаковывается общеязыковой среды выполнения (CLR), то он инкапсулирует значение в `System.Object` и сохраняет его в управляемой куче. Операция распаковки извлекает тип значения из объекта. Упаковка является неявной; распаковка является явной.  
  
## <a name="related-articles"></a>Связанные статьи  
  
|Заголовок|Описание:|  
|-----------|-----------------|  
|[Практическое руководство. Явный запрос упаковки-преобразования](../dotnet/how-to-explicitly-request-boxing.md)|Описывает способ явного запроса на преобразование для переменной.|  
|[Практическое руководство. Использование gcnew для создания типов значений и использование неявной упаковки-преобразования](../dotnet/how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing.md)|Показано, как использовать `gcnew` для создания тип упакованного значения, который может быть размещен в куче, управляемая и сбора мусора.|  
|[Практическое руководство. Распаковка-преобразование](../dotnet/how-to-unbox.md)|Показано, как распаковать и измените значение.|  
|[Стандартные преобразования и неявная упаковка-преобразование](../dotnet/standard-conversions-and-implicit-boxing.md)|Показывает, что стандартное преобразование выбран компилятором через преобразование, которое требуется упаковка.|  
|[Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)|Статья верхнего уровня для программирования .NET в документацию по Visual C++.|