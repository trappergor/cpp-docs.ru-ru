---
title: Команда обработчики для прокрутки (доступ к данным MFC) записей | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- record views [C++], scrolling
- record scrolling [C++]
- scrolling records
ms.assetid: f8b13477-2a37-459e-a30c-806fb78165ac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ef2b57bd37441b9a35c26ab36fcf3cb15cd0d878
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340332"
---
# <a name="command-handlers-for-record-scrolling--mfc-data-access"></a>Обработчики команд для прокрутки записей (доступ к данным MFC) 
[CRecordView](../mfc/reference/crecordview-class.md) класс предоставляет обработку по умолчанию для следующих стандартных команд:  
  
-   ID_RECORD_MOVE_FIRST  
  
-   ID_RECORD_MOVE_LAST  
  
-   ID_RECORD_MOVE_NEXT  
  
-   ID_RECORD_MOVE_PREV  
  
 `OnMove` Функция-член предоставляет обработку по умолчанию для всех четырех команд, при переходе от записи к записи. Если команды даны, RFX (или DFX) загружает новую запись в поля набора записей и DDX передвигает значения в элементы управления формы записи. Дополнительные сведения о RFX см. в разделе [обмен полей записей (RFX)](../data/odbc/record-field-exchange-rfx.md).  
  
> [!NOTE]
>  Обязательно используйте стандартные идентификаторы команд для любых объектов пользовательского интерфейса, связанных с стандартными командами перехода к записи.  
  
## <a name="see-also"></a>См. также  
 [Поддержка навигации в представлении записей](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)