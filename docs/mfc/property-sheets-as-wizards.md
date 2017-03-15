---
title: "Вкладки свойств как мастера | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "страницы свойств, как мастеры"
ms.assetid: 1ea66ecb-23b0-484a-838d-58671a2999b5
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Вкладки свойств как мастера
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ключ характеристика страницы свойств мастера, что переход связан с далее или завершение, back и Отмены вместо вкладок.  Необходимо вызвать [CPropertySheet::SetWizardMode](../Topic/CPropertySheet::SetWizardMode.md) перед вызовом [CPropertySheet::DoModal](../Topic/CPropertySheet::DoModal.md) в объекте страницы свойств для использования этой функции.  
  
 Пользователь получает те же [CPropertyPage::OnSetActive](../Topic/CPropertyPage::OnSetActive.md) и уведомления [CPropertyPage::OnKillActive](../Topic/CPropertyPage::OnKillActive.md) при перемещении с одной страницы на другую страницу.  Далее кнопки и завершения взаимноисключающих управления; то есть только одно из них будет отображаться одновременно.  На первой странице, следующую кнопку должна быть включена.  Если пользователь на последней странице, кнопку завершения должна быть включена.  Это не выполняется автоматически средой выполнения.  Необходимо вызвать [CPropertySheet::SetWizardButton](../Topic/CPropertySheet::SetWizardButtons.md) на последней странице для этого параметру.  
  
 Показать все кнопки по умолчанию необходимо показать mush кнопку завершения перемещения следующую кнопку.  Затем переместите сначала кнопку, чтобы будет поддерживается относительная его положение в следующую кнопку.  Дополнительные объяснения, поиска статьи Q143210 КБ.  Статьи базы знаний можно найти в библиотеке MSDN.  
  
## Пример  
 [!code-cpp[NVC_MFCDocView#5](../mfc/codesnippet/CPP/property-sheets-as-wizards_1.cpp)]  
  
## См. также  
 [Страницы свойств](../mfc/property-sheets-mfc.md)