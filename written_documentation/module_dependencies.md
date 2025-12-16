# Module Dependency Analysis

## Top 30 Modules with Most Dependents

| Module | Dependents |
|---|---|
| [`account`](odoo/addons/account) | 149 |
| [`base`](odoo/odoo/addons/base) | 44 |
| [`mail`](odoo/addons/mail) | 43 |
| [`account_edi_ubl_cii`](odoo/addons/account_edi_ubl_cii) | 42 |
| [`base_vat`](odoo/addons/base_vat) | 40 |
| [`web`](odoo/addons/web) | 37 |
| [`point_of_sale`](odoo/addons/point_of_sale) | 36 |
| [`base_iban`](odoo/addons/base_iban) | 25 |
| [`payment`](odoo/addons/payment) | 21 |
| [`sale`](odoo/addons/sale) | 21 |
| [`website`](odoo/addons/website) | 20 |
| [`base_setup`](odoo/addons/base_setup) | 19 |
| [`hr`](odoo/addons/hr) | 18 |
| [`portal`](odoo/addons/portal) | 17 |
| [`sms`](odoo/addons/sms) | 17 |
| [`l10n_syscohada`](odoo/addons/l10n_syscohada) | 17 |
| [`website_sale`](odoo/addons/website_sale) | 16 |
| [`crm`](odoo/addons/crm) | 15 |
| [`digest`](odoo/addons/digest) | 13 |
| [`spreadsheet_dashboard`](odoo/addons/spreadsheet_dashboard) | 13 |
| [`mass_mailing`](odoo/addons/mass_mailing) | 13 |
| [`stock`](odoo/addons/stock) | 11 |
| [`web_tour`](odoo/addons/web_tour) | 10 |
| [`stock_account`](odoo/addons/stock_account) | 10 |
| [`sale_stock`](odoo/addons/sale_stock) | 10 |
| [`mrp`](odoo/addons/mrp) | 10 |
| [`resource`](odoo/addons/resource) | 9 |
| [`calendar`](odoo/addons/calendar) | 9 |
| [`event`](odoo/addons/event) | 9 |
| [`sale_management`](odoo/addons/sale_management) | 9 |

## Likely Base Layers
Modules with many dependents but few dependencies (<= 3).

| Module | Dependents | Dependencies |
|---|---|---|
| [`base`](odoo/odoo/addons/base) | 44 | None |
| [`account_edi_ubl_cii`](odoo/addons/account_edi_ubl_cii) | 42 | [`account`](odoo/addons/account) |
| [`base_vat`](odoo/addons/base_vat) | 40 | [`account`](odoo/addons/account) |
| [`web`](odoo/addons/web) | 37 | [`base`](odoo/odoo/addons/base) |
| [`base_iban`](odoo/addons/base_iban) | 25 | [`account`](odoo/addons/account), [`web`](odoo/addons/web) |
| [`payment`](odoo/addons/payment) | 21 | [`onboarding`](odoo/addons/onboarding), [`portal`](odoo/addons/portal) |
| [`sale`](odoo/addons/sale) | 21 | [`sales_team`](odoo/addons/sales_team), [`account_payment`](odoo/addons/account_payment), [`utm`](odoo/addons/utm) |
| [`base_setup`](odoo/addons/base_setup) | 19 | [`base`](odoo/odoo/addons/base), [`web`](odoo/addons/web) |
| [`l10n_syscohada`](odoo/addons/l10n_syscohada) | 17 | [`account`](odoo/addons/account) |
| [`digest`](odoo/addons/digest) | 13 | [`mail`](odoo/addons/mail), [`portal`](odoo/addons/portal), [`resource`](odoo/addons/resource) |
| [`spreadsheet_dashboard`](odoo/addons/spreadsheet_dashboard) | 13 | [`spreadsheet`](odoo/addons/spreadsheet) |
| [`stock`](odoo/addons/stock) | 11 | [`product`](odoo/addons/product), [`barcodes_gs1_nomenclature`](odoo/addons/barcodes_gs1_nomenclature), [`digest`](odoo/addons/digest) |
| [`web_tour`](odoo/addons/web_tour) | 10 | [`web`](odoo/addons/web) |
| [`stock_account`](odoo/addons/stock_account) | 10 | [`stock`](odoo/addons/stock), [`account`](odoo/addons/account) |
| [`sale_stock`](odoo/addons/sale_stock) | 10 | [`sale`](odoo/addons/sale), [`stock_account`](odoo/addons/stock_account) |
| [`mrp`](odoo/addons/mrp) | 10 | [`product`](odoo/addons/product), [`stock`](odoo/addons/stock), [`resource`](odoo/addons/resource) |
| [`resource`](odoo/addons/resource) | 9 | [`base`](odoo/odoo/addons/base), [`web`](odoo/addons/web) |
| [`calendar`](odoo/addons/calendar) | 9 | [`base`](odoo/odoo/addons/base), [`mail`](odoo/addons/mail) |
| [`sale_management`](odoo/addons/sale_management) | 9 | [`sale`](odoo/addons/sale), [`digest`](odoo/addons/digest) |
| [`utm`](odoo/addons/utm) | 8 | [`base`](odoo/odoo/addons/base), [`web`](odoo/addons/web) |
| [`hr_holidays`](odoo/addons/hr_holidays) | 8 | [`hr`](odoo/addons/hr), [`calendar`](odoo/addons/calendar), [`resource`](odoo/addons/resource) |
| [`html_editor`](odoo/addons/html_editor) | 8 | [`base`](odoo/odoo/addons/base), [`bus`](odoo/addons/bus), [`web`](odoo/addons/web) |
| [`l10n_gcc_invoice`](odoo/addons/l10n_gcc_invoice) | 8 | [`account`](odoo/addons/account) |
| [`l10n_din5008`](odoo/addons/l10n_din5008) | 8 | [`account`](odoo/addons/account) |
| [`account_debit_note`](odoo/addons/account_debit_note) | 8 | [`account`](odoo/addons/account) |
| [`contacts`](odoo/addons/contacts) | 7 | [`base`](odoo/odoo/addons/base), [`mail`](odoo/addons/mail) |
| [`iap_mail`](odoo/addons/iap_mail) | 7 | [`iap`](odoo/addons/iap), [`mail`](odoo/addons/mail) |
| [`l10n_latam_base`](odoo/addons/l10n_latam_base) | 7 | [`contacts`](odoo/addons/contacts), [`base_vat`](odoo/addons/base_vat) |
| [`pos_restaurant`](odoo/addons/pos_restaurant) | 7 | [`point_of_sale`](odoo/addons/point_of_sale) |
| [`purchase`](odoo/addons/purchase) | 7 | [`account`](odoo/addons/account) |
| [`purchase_stock`](odoo/addons/purchase_stock) | 7 | [`stock_account`](odoo/addons/stock_account), [`purchase`](odoo/addons/purchase) |
| [`mass_mailing_sms`](odoo/addons/mass_mailing_sms) | 7 | [`portal`](odoo/addons/portal), [`mass_mailing`](odoo/addons/mass_mailing), [`sms`](odoo/addons/sms) |
| [`pos_self_order`](odoo/addons/pos_self_order) | 7 | [`pos_restaurant`](odoo/addons/pos_restaurant), [`http_routing`](odoo/addons/http_routing), [`link_tracker`](odoo/addons/link_tracker) |
| [`auth_signup`](odoo/addons/auth_signup) | 6 | [`base_setup`](odoo/addons/base_setup), [`mail`](odoo/addons/mail), [`web`](odoo/addons/web) |
| [`phone_validation`](odoo/addons/phone_validation) | 6 | [`base`](odoo/odoo/addons/base), [`mail`](odoo/addons/mail) |
| [`event_sale`](odoo/addons/event_sale) | 6 | [`event_product`](odoo/addons/event_product), [`sale_management`](odoo/addons/sale_management) |

## Core Dependency Backbone (Mermaid)

```mermaid
%%{ init: { 'flowchart': { 'curve': 'step', 'nodeSpacing': 100, 'rankSpacing': 150 } } }%%
graph LR;
    classDef base fill:#f5f5f5,stroke:#616161,stroke-width:2px,color:#333,padding:20px;
    classDef web fill:#e3f2fd,stroke:#1565c0,stroke-width:2px,color:#333,padding:20px;
    classDef account fill:#e8f5e9,stroke:#2e7d32,stroke-width:2px,color:#333,padding:20px;
    classDef sale fill:#fff3e0,stroke:#ef6c00,stroke-width:2px,color:#333,padding:20px;
    classDef stock fill:#f3e5f5,stroke:#7b1fa2,stroke-width:2px,color:#333,padding:20px;
    classDef mrp fill:#ffebee,stroke:#c62828,stroke-width:2px,color:#333,padding:20px;
    classDef hr fill:#e0f7fa,stroke:#00838f,stroke-width:2px,color:#333,padding:20px;
    classDef pos fill:#fffde7,stroke:#fbc02d,stroke-width:2px,color:#333,padding:20px;
    classDef marketing fill:#fce4ec,stroke:#c2185b,stroke-width:2px,color:#333,padding:20px;
    classDef l10n fill:#e8eaf6,stroke:#3949ab,stroke-width:2px,color:#333,padding:20px;
    classDef productivity fill:#f9fbe7,stroke:#827717,stroke-width:2px,color:#333,padding:20px;
    classDef other fill:#ffffff,stroke:#9e9e9e,stroke-width:1px,stroke-dasharray: 5 5,color:#333,padding:20px;
    subgraph cluster_base ["BASE"]
        base_vat
        base_setup
        base_iban
        base
    end
    class base_vat,base_setup,base_iban,base base;
    subgraph cluster_web ["WEB"]
        portal
        website_sale
        web
        web_tour
    end
    class portal,website_sale,web,web_tour web;
    subgraph cluster_account ["ACCOUNT"]
        account
        payment
        account_edi_ubl_cii
    end
    class account,payment,account_edi_ubl_cii account;
    subgraph cluster_sale ["SALE"]
        sale
        sale_stock
        sale_management
    end
    class sale,sale_stock,sale_management sale;
    subgraph cluster_stock ["STOCK"]
        stock
        stock_account
    end
    class stock,stock_account stock;
    subgraph cluster_mrp ["MRP"]
        mrp
    end
    class mrp mrp;
    subgraph cluster_hr ["HR"]
        hr
    end
    class hr hr;
    subgraph cluster_apps ["MISC APPS"]
        direction TB
        subgraph cluster_pos ["POS"]
            point_of_sale
        end
        class point_of_sale pos;
        subgraph cluster_marketing ["MARKETING"]
            mass_mailing
            crm
            sms
        end
        class mass_mailing,crm,sms marketing;
        subgraph cluster_l10n ["L10N"]
            l10n_syscohada
        end
        class l10n_syscohada l10n;
        subgraph cluster_productivity ["PRODUCTIVITY"]
            resource
            event
            calendar
            digest
            spreadsheet_dashboard
        end
        class resource,event,calendar,digest,spreadsheet_dashboard productivity;
        subgraph cluster_other ["OTHER"]
            website
            mail
        end
        class website,mail other;
    end
    resource --> base;
    resource --> web;
    sale_stock --> sale;
    sale_stock --> stock_account;
    portal --> web;
    portal --> mail;
    stock --> digest;
    base_vat --> account;
    sale_management --> sale;
    sale_management --> digest;
    base_setup --> base;
    base_setup --> web;
    event --> base_setup;
    event --> mail;
    event --> portal;
    calendar --> base;
    calendar --> mail;
    hr --> base_setup;
    hr --> digest;
    hr --> web;
    website_sale --> website;
    website_sale --> sale;
    website_sale --> digest;
    base_iban --> account;
    base_iban --> web;
    web --> base;
    account --> base_setup;
    account --> portal;
    account --> digest;
    web_tour --> web;
    l10n_syscohada --> account;
    point_of_sale --> resource;
    point_of_sale --> stock_account;
    point_of_sale --> digest;
    payment --> portal;
    digest --> mail;
    digest --> portal;
    digest --> resource;
    mrp --> stock;
    mrp --> resource;
    website --> digest;
    website --> web;
    website --> portal;
    website --> mail;
    account_edi_ubl_cii --> account;
    mass_mailing --> mail;
    mass_mailing --> web_tour;
    mass_mailing --> digest;
    crm --> base_setup;
    crm --> mail;
    crm --> calendar;
    crm --> resource;
    crm --> web_tour;
    crm --> digest;
    sms --> base;
    sms --> mail;
    mail --> base;
    mail --> base_setup;
    mail --> web_tour;
    stock_account --> stock;
    stock_account --> account;
    linkStyle 0,1,12,13,14,15,16,35,36,37 stroke:#827717,stroke-width:2px;
    linkStyle 2,3,8,9 stroke:#ef6c00,stroke-width:2px;
    linkStyle 4,5,20,21,22,25,29 stroke:#1565c0,stroke-width:2px;
    linkStyle 6,59,60 stroke:#7b1fa2,stroke-width:2px;
    linkStyle 7,10,11,23,24 stroke:#616161,stroke-width:2px;
    linkStyle 17,18,19 stroke:#00838f,stroke-width:2px;
    linkStyle 26,27,28,34,44 stroke:#2e7d32,stroke-width:2px;
    linkStyle 30 stroke:#3949ab,stroke-width:2px;
    linkStyle 31,32,33 stroke:#fbc02d,stroke-width:2px;
    linkStyle 38,39 stroke:#c62828,stroke-width:2px;
    linkStyle 40,41,42,43,56,57,58 stroke:#9e9e9e,stroke-width:2px;
    linkStyle 45,46,47,48,49,50,51,52,53,54,55 stroke:#c2185b,stroke-width:2px;

    click sale "odoo/addons/sale" "Open sale module";
    click resource "odoo/addons/resource" "Open resource module";
    click sale_stock "odoo/addons/sale_stock" "Open sale_stock module";
    click portal "odoo/addons/portal" "Open portal module";
    click stock "odoo/addons/stock" "Open stock module";
    click base_vat "odoo/addons/base_vat" "Open base_vat module";
    click sale_management "odoo/addons/sale_management" "Open sale_management module";
    click base_setup "odoo/addons/base_setup" "Open base_setup module";
    click event "odoo/addons/event" "Open event module";
    click calendar "odoo/addons/calendar" "Open calendar module";
    click hr "odoo/addons/hr" "Open hr module";
    click website_sale "odoo/addons/website_sale" "Open website_sale module";
    click base_iban "odoo/addons/base_iban" "Open base_iban module";
    click account "odoo/addons/account" "Open account module";
    click web "odoo/addons/web" "Open web module";
    click web_tour "odoo/addons/web_tour" "Open web_tour module";
    click l10n_syscohada "odoo/addons/l10n_syscohada" "Open l10n_syscohada module";
    click point_of_sale "odoo/addons/point_of_sale" "Open point_of_sale module";
    click payment "odoo/addons/payment" "Open payment module";
    click digest "odoo/addons/digest" "Open digest module";
    click mrp "odoo/addons/mrp" "Open mrp module";
    click website "odoo/addons/website" "Open website module";
    click base "odoo/odoo/addons/base" "Open base module";
    click account_edi_ubl_cii "odoo/addons/account_edi_ubl_cii" "Open account_edi_ubl_cii module";
    click mass_mailing "odoo/addons/mass_mailing" "Open mass_mailing module";
    click crm "odoo/addons/crm" "Open crm module";
    click stock_account "odoo/addons/stock_account" "Open stock_account module";
    click mail "odoo/addons/mail" "Open mail module";
    click sms "odoo/addons/sms" "Open sms module";
    click spreadsheet_dashboard "odoo/addons/spreadsheet_dashboard" "Open spreadsheet_dashboard module";
```
