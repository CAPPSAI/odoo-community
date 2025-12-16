# Override Map: `sale.order`

**Target Model**: `sale.order`
**Active Modules**: 37
*(Localization modules `l10n_*` have been excluded)*

## 🔥 Hot Override Points (Global)

Methods overridden by the most modules (Top 15).

| Method | Override Count |
|---|---|
| `action_confirm` | 10 |
| `_verify_updated_quantity` | 7 |
| `_action_confirm` | 6 |
| `_action_cancel` | 4 |
| `_cart_find_product_line` | 4 |
| `_check_cart_is_ready_to_be_paid` | 4 |
| `_remove_delivery_line` | 3 |
| `write` | 3 |
| `create` | 3 |
| `_compute_warehouse_id` | 3 |
| `_prepare_order_line_values` | 3 |
| `_cart_update_order_line` | 3 |
| `_filter_can_send_abandoned_cart_mail` | 3 |
| `_set_delivery_method` | 3 |
| `_compute_partner_shipping_id` | 2 |

## 🏗️ Core / Functional Overrides
_Modules that implement business logic (Stock, Sales, EDI, etc.)_

### 📦 `delivery`

- **File**: `odoo/addons/delivery/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Added Fields**: pickup_location_data (_Json_), carrier_id (_Many2one_), delivery_message (_Char_), delivery_set (_Boolean_), recompute_delivery_price (_Boolean_), is_all_service (_Boolean_), shipping_weight (_Float_)
  - **Methods**:
    - `_compute_partner_shipping_id`
    - `_compute_is_service_products (@depends)`
    - `_compute_amount_total_without_delivery`
    - `_compute_delivery_state (@depends)`
    - `onchange_order_line (@onchange)`
    - `_get_update_prices_lines`
    - `_remove_delivery_line`
    - `set_delivery_line`
    - `_set_pickup_location`
    - `_get_pickup_locations`
    - `action_open_delivery_wizard`
    - `_action_confirm`
    - `_prepare_delivery_line_vals`
    - `_create_delivery_line`
    - `_compute_shipping_weight (@depends)`
    - `_get_estimated_weight`
    - `_update_order_line_info`
- **File**: `odoo/addons/delivery/views/sale_order_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`view_order_form_with_carrier`](odoo/addons/delivery/views/sale_order_views.xml#L4) -> `sale.view_order_form`

### 📦 `delivery_mondialrelay`

- **File**: `odoo/addons/delivery_mondialrelay/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Methods**: `action_confirm`

### 📦 `event_booth_sale`

- **File**: `odoo/addons/event_booth_sale/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Added Fields**: event_booth_ids (_One2many_), event_booth_count (_Integer_)
  - **Methods**:
    - `_compute_event_booth_count (@depends)`
    - `action_confirm`
    - `action_view_booth_list`
    - `_get_product_catalog_domain`
- **File**: `odoo/addons/event_booth_sale/views/sale_order_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`sale_order_view_form`](odoo/addons/event_booth_sale/views/sale_order_views.xml#L4) -> `event_sale.sale_order_view_form`

### 📦 `event_sale`

- **File**: `odoo/addons/event_sale/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Added Fields**: attendee_count (_Integer_)
  - **Methods**: `write`, `action_confirm`, `action_view_attendee_list`, `_compute_attendee_count`, `_get_product_catalog_domain`
- **File**: `odoo/addons/event_sale/views/sale_order_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`sale_order_view_form`](odoo/addons/event_sale/views/sale_order_views.xml#L3) -> `sale.view_order_form`

### 📦 `mass_mailing_sale`

- **File**: `odoo/addons/mass_mailing_sale/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Methods**: `_mailing_get_default_domain`

### 📦 `partnership`

- **File**: `odoo/addons/partnership/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Added Fields**: assigned_grade_id (_Many2one_)
  - **Methods**:
    - `_constraint_unique_assigned_grade (@constrains)`
    - `_compute_partnership (@depends)`
    - `action_confirm`
    - `_add_partnership`

### 📦 `pos_sale`

- **File**: `odoo/addons/pos_sale/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Added Fields**: pos_order_line_ids (_One2many_), pos_order_count (_Integer_), amount_unpaid (_Monetary_)
  - **Methods**:
    - `_load_pos_data_domain (@model)`
    - `_load_pos_data_fields (@model)`
    - `load_sale_order_from_pos`
    - `_count_pos_order`
    - `action_view_pos_order`
    - `_compute_amount_unpaid (@depends)`
    - `_compute_amount_to_invoice (@depends)`
    - `_compute_amount_invoiced (@depends)`
    - `_prepare_down_payment_line_values_from_base_line`
- **File**: `odoo/addons/pos_sale/views/sale_order_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`view_order_form_inherit_pos_sale`](odoo/addons/pos_sale/views/sale_order_views.xml#L4) -> `sale.view_order_form`

### 📦 `repair`

- **File**: `odoo/addons/repair/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Added Fields**: repair_order_ids (_One2many_), repair_count (_Integer_)
  - **Methods**:
    - `_compute_repair_count (@depends)`
    - `_action_cancel`
    - `_action_confirm`
    - `action_show_repair`
- **File**: `odoo/addons/repair/views/sale_order_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`view_sale_order_form_inherit_repair`](odoo/addons/repair/views/sale_order_views.xml#L4) -> `sale.view_order_form`

### 📦 `sale`

- **File**: `odoo/addons/sale/views/sale_order_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`sale_order_kanban_upload`](odoo/addons/sale/views/sale_order_views.xml#L98) -> `view_sale_order_kanban`
    - [`view_order_tree`](odoo/addons/sale/views/sale_order_views.xml#L179) -> `sale_order_tree`
    - [`sale_order_list_upload`](odoo/addons/sale/views/sale_order_views.xml#L193) -> `view_order_tree`
    - [`view_quotation_tree`](odoo/addons/sale/views/sale_order_views.xml#L206) -> `sale_order_tree`
    - [`view_quotation_tree_with_onboarding`](odoo/addons/sale/views/sale_order_views.xml#L228) -> `view_quotation_tree`
    - [`view_quotation_kanban_with_onboarding`](odoo/addons/sale/views/sale_order_views.xml#L240) -> `view_sale_order_kanban`
    - [`sale_order_view_search_inherit_quotation`](odoo/addons/sale/views/sale_order_views.xml#L965) -> `sale.view_sales_order_filter`
    - [`sale_order_view_search_inherit_sale`](odoo/addons/sale/views/sale_order_views.xml#L984) -> `sale.view_sales_order_filter`

### 📦 `sale_crm`

- **File**: `odoo/addons/sale_crm/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Added Fields**: opportunity_id (_Many2one_)
  - **Methods**: `action_confirm`
- **File**: `odoo/addons/sale_crm/views/sale_order_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`sale_view_inherit123`](odoo/addons/sale_crm/views/sale_order_views.xml#L12) -> `sale.view_order_form`

### 📦 `sale_edi_ubl`

- **File**: `odoo/addons/sale_edi_ubl/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Methods**:
    - `_get_edi_builders`
    - `_get_import_file_type`
    - `_get_edi_decoder`
    - `_create_activity_set_details`
    - `_get_line_vals_list (@model)`

### 📦 `sale_expense`

- **File**: `odoo/addons/sale_expense/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Added Fields**: expense_ids (_One2many_), expense_count (_Integer_)
  - **Methods**:
    - `_search_display_name (@model)`
    - `_compute_expense_count (@depends)`
- **File**: `odoo/addons/sale_expense/views/sale_order_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`sale_order_form_view_inherit`](odoo/addons/sale_expense/views/sale_order_views.xml#L4) -> `sale.view_order_form`

### 📦 `sale_gelato`

- **File**: `odoo/addons/sale_gelato/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Methods**:
    - `_prevent_mixing_gelato_and_non_gelato_products`
    - `action_open_delivery_wizard`
    - `action_confirm`
    - `_ensure_partner_address_is_complete`
    - `_create_order_on_gelato`
    - `_gelato_prepare_items_payload`
    - `_confirm_order_on_gelato (@post_commit)`
    - `_delete_order_on_gelato (@post_commit)`

### 📦 `sale_loyalty`

- **File**: `odoo/addons/sale_loyalty/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Added Fields**: applied_coupon_ids (_Many2many_), code_enabled_rule_ids (_Many2many_), coupon_point_ids (_One2many_), reward_amount (_Float_), gift_card_count (_Integer_), loyalty_data (_Json_)
  - **Methods**:
    - `_compute_reward_total (@depends)`
    - `_compute_loyalty_data`
    - `_compute_gift_card_count`
    - `_add_loyalty_history_lines`
    - `_get_no_effect_on_threshold_lines`
    - `copy`
    - `action_confirm`
    - `_action_cancel`
    - `action_open_reward_wizard`
    - `action_view_gift_cards`
    - `_send_reward_coupon_mail`
    - `_get_applied_global_discount_lines`
    - `_get_applied_global_discount`
    - `_get_reward_values_product`
    - `_discountable_amount`
    - `_discountable_order`
    - `_cheapest_line`
    - `_discountable_cheapest`
    - `_get_specific_discountable_lines`
    - `_discountable_specific`
    - `_get_reward_values_discount`
    - `_get_program_domain`
    - `_get_trigger_domain`
    - `_get_program_timezone`
    - `_get_confirmed_tx_create_date`
    - `_get_applicable_program_points`
    - `_get_points_programs`
    - `_get_reward_programs`
    - `_get_reward_coupons`
    - `_get_applied_programs`
    - `_recompute_prices`
    - `_get_point_changes`
    - `_get_real_points_for_coupon`
    - `_add_points_for_coupon`
    - `_update_loyalty_history`
    - `_remove_program_from_points`
    - `_get_reward_line_values`
    - `_write_vals_from_reward_vals`
    - `_best_global_discount_already_applied`
    - `_get_discount_amount`
    - `_apply_program_reward`
    - `_get_claimable_rewards`
    - `_allow_nominative_programs`
    - `_update_programs_and_rewards`
    - `_get_not_rewarded_order_lines`
    - `_get_order_line_price`
    - `_program_check_compute_points`
    - `__try_apply_program`
    - `_try_apply_program`
    - `_try_apply_code`
    - `_validate_order`
- **File**: `odoo/addons/sale_loyalty/views/sale_order_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`sale_order_view_form_inherit_sale_loyalty`](odoo/addons/sale_loyalty/views/sale_order_views.xml#L4) -> `sale.view_order_form`

### 📦 `sale_loyalty_delivery`

- **File**: `odoo/addons/sale_loyalty_delivery/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Methods**:
    - `_compute_amount_total_without_delivery`
    - `_get_no_effect_on_threshold_lines`
    - `_get_not_rewarded_order_lines`
    - `_get_reward_values_free_shipping`
    - `_get_reward_line_values`
    - `_get_claimable_rewards`

### 📦 `sale_management`

- **File**: `odoo/addons/sale_management/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Added Fields**: sale_order_template_id (_Many2one_)
  - **Methods**:
    - `_compute_sale_order_template_id`
    - `_compute_note (@depends)`
    - `_compute_require_signature (@depends)`
    - `_compute_require_payment (@depends)`
    - `_compute_prepayment_percent (@depends)`
    - `_compute_validity_date (@depends)`
    - `_compute_journal_id (@depends)`
    - `_onchange_company_id (@onchange)`
    - `_onchange_sale_order_template_id (@onchange)`
    - `_onchange_partner_id (@onchange)`
    - `_get_confirmation_template`
    - `action_confirm`
- **File**: `odoo/addons/sale_management/views/sale_order_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`sale_order_form_quote`](odoo/addons/sale_management/views/sale_order_views.xml#L4) -> `sale.view_order_form`

### 📦 `sale_margin`

- **File**: `odoo/addons/sale_margin/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Added Fields**: margin (_Monetary_), margin_percent (_Float_)
  - **Methods**:
    - `_compute_margin (@depends)`
- **File**: `odoo/addons/sale_margin/views/sale_order_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`sale_margin_sale_order`](odoo/addons/sale_margin/views/sale_order_views.xml#L4) -> `sale.view_order_form`
    - [`sale_margin_sale_order_pivot`](odoo/addons/sale_margin/views/sale_order_views.xml#L35) -> `sale.view_sale_order_pivot`
    - [`sale_margin_sale_order_graph`](odoo/addons/sale_margin/views/sale_order_views.xml#L46) -> `sale.view_sale_order_graph`

### 📦 `sale_mrp`

- **File**: `odoo/addons/sale_mrp/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Added Fields**: mrp_production_count (_Integer_), mrp_production_ids (_Many2many_)
  - **Methods**:
    - `_compute_mrp_production_ids (@depends)`
    - `action_view_mrp_production`
- **File**: `odoo/addons/sale_mrp/views/sale_order_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`sale_order_form_mrp`](odoo/addons/sale_mrp/views/sale_order_views.xml#L4) -> `sale.view_order_form`

### 📦 `sale_pdf_quote_builder`

- **File**: `odoo/addons/sale_pdf_quote_builder/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Added Fields**: available_quotation_document_ids (_Many2many_), is_pdf_quote_builder_available (_Boolean_), quotation_document_ids (_Many2many_), customizable_pdf_form_fields (_Json_)
  - **Methods**:
    - `_default_quotation_document_ids`
    - `_compute_available_quotation_document_ids (@depends)`
    - `_compute_is_pdf_quote_builder_available (@depends)`
    - `_onchange_sale_order_template_id (@onchange)`
    - `get_update_included_pdf_params`
- **File**: `odoo/addons/sale_pdf_quote_builder/views/sale_order_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`sale_order_form_inherit_sale_pdf_quote_builder`](odoo/addons/sale_pdf_quote_builder/views/sale_order_views.xml#L4) -> `sale_management.sale_order_form_quote`

### 📦 `sale_product_matrix`

- **File**: `odoo/addons/sale_product_matrix/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Added Fields**: report_grids (_Boolean_), grid_product_tmpl_id (_Many2one_), grid_update (_Boolean_), grid (_Char_)
  - **Methods**:
    - `_set_grid_up (@onchange)`
    - `_apply_grid (@onchange)`
    - `_get_matrix`
    - `get_report_matrixes`
- **File**: `odoo/addons/sale_product_matrix/views/sale_order_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`view_order_form_with_variant_grid`](odoo/addons/sale_product_matrix/views/sale_order_views.xml#L4) -> `sale.view_order_form`

### 📦 `sale_project`

- **File**: `odoo/addons/sale_project/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Added Fields**: tasks_ids (_Many2many_), tasks_count (_Integer_), visible_project (_Boolean_), project_ids (_Many2many_), project_count (_Integer_), milestone_count (_Integer_), is_product_milestone (_Boolean_), show_create_project_button (_Boolean_), show_project_button (_Boolean_), closed_task_count (_Integer_), completed_task_percentage (_Float_), project_id (_Many2one_), project_account_id (_Many2one_)
  - **Methods**:
    - `default_get (@model)`
    - `_compute_milestone_count`
    - `_compute_is_product_milestone`
    - `_compute_show_project_and_task_button`
    - `_search_tasks_ids (@model)`
    - `_compute_tasks_ids (@depends)`
    - `_compute_visible_project (@depends)`
    - `_compute_project_ids (@depends)`
    - `_action_confirm`
    - `_tasks_ids_domain`
    - `action_create_project`
    - `action_view_project_ids`
    - `action_view_milestone`
    - `create (@model_create_multi)`
    - `write`
    - `_compute_completed_task_percentage`
    - `action_confirm`
    - `get_first_service_line`
- **File**: `odoo/addons/sale_project/views/sale_order_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`view_order_form_inherit_sale_project`](odoo/addons/sale_project/views/sale_order_views.xml#L4) -> `sale.view_order_form`
    - [`view_sales_order_filter_inherit_sale_project`](odoo/addons/sale_project/views/sale_order_views.xml#L52) -> `sale.view_sales_order_filter`
    - [`view_order_simple_form`](odoo/addons/sale_project/views/sale_order_views.xml#L72) -> `sale.view_order_form`

### 📦 `sale_purchase`

- **File**: `odoo/addons/sale_purchase/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Added Fields**: purchase_order_count (_Integer_)
  - **Methods**:
    - `_compute_purchase_order_count (@depends)`
    - `_action_confirm`
    - `_action_cancel`
    - `action_view_purchase_orders`
    - `_get_purchase_orders`
    - `_activity_cancel_on_purchase`
- **File**: `odoo/addons/sale_purchase/views/sale_order_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`sale_order_inherited_form_purchase`](odoo/addons/sale_purchase/views/sale_order_views.xml#L4) -> `sale.view_order_form`

### 📦 `sale_purchase_stock`

- **File**: `odoo/addons/sale_purchase_stock/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Methods**:
    - `_compute_purchase_order_count (@depends)`
    - `_get_purchase_orders`

### 📦 `sale_stock`

- **File**: `odoo/addons/sale_stock/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Added Fields**: incoterm (_Many2one_), incoterm_location (_Char_), picking_policy (_Selection_), warehouse_id (_Many2one_), picking_ids (_One2many_), delivery_count (_Integer_), delivery_status (_Selection_), late_availability (_Boolean_), stock_reference_ids (_Many2many_), effective_date (_Datetime_), expected_date (_Datetime_), json_popover (_Char_), show_json_popover (_Boolean_)
  - **Methods**:
    - `_init_column`
    - `_compute_effective_date (@depends)`
    - `_compute_delivery_status (@depends)`
    - `_compute_expected_date (@depends)`
    - `_compute_late_availability (@depends)`
    - `_search_late_availability`
    - `_select_expected_date`
    - `_check_warehouse (@constrains)`
    - `write`
    - `_compute_json_popover`
    - `_action_confirm`
    - `_compute_picking_ids (@depends)`
    - `_compute_warehouse_id (@depends)`
    - `_onchange_partner_shipping_id (@onchange)`
    - `action_view_delivery`
    - `_action_cancel`
    - `_get_action_view_picking`
    - `_prepare_invoice`
    - `_log_decrease_ordered_quantity`
    - `_is_display_stock_in_catalog`
    - `_add_reference`
    - `_remove_reference`
- **File**: `odoo/addons/sale_stock/views/sale_order_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`view_order_form_inherit_sale_stock`](odoo/addons/sale_stock/views/sale_order_views.xml#L4) -> `sale.view_order_form`
    - [`sale_order_tree`](odoo/addons/sale_stock/views/sale_order_views.xml#L65) -> `sale.sale_order_tree`
    - [`view_order_tree`](odoo/addons/sale_stock/views/sale_order_views.xml#L82) -> `sale.view_order_tree`
    - [`sale_stock_sale_order_view_search_inherit`](odoo/addons/sale_stock/views/sale_order_views.xml#L115) -> `sale.sale_order_view_search_inherit_sale`

### 📦 `sale_timesheet`

- **File**: `odoo/addons/sale_timesheet/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Added Fields**: timesheet_count (_Float_), timesheet_encode_uom_id (_Many2one_), timesheet_total_duration (_Integer_), show_hours_recorded_button (_Boolean_)
  - **Methods**:
    - `_compute_timesheet_count`
    - `_compute_timesheet_total_duration (@depends)`
    - `_compute_field_value`
    - `_compute_show_hours_recorded_button`
    - `create (@model_create_multi)`
    - `_get_order_with_valid_service_product`
    - `_get_prepaid_service_lines_to_upsell`
    - `action_view_timesheet`
    - `_reset_has_displayed_warning_upsell_order_lines`
    - `_create_invoices`
- **File**: `odoo/addons/sale_timesheet/views/sale_order_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`view_order_form_inherit_sale_timesheet`](odoo/addons/sale_timesheet/views/sale_order_views.xml#L4) -> `sale_project.view_order_form_inherit_sale_project`

### 📦 `stock_delivery`

- **File**: `odoo/addons/stock_delivery/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Methods**: `set_delivery_line`, `_create_delivery_line`, `_format_currency_amount`

### 📦 `stock_dropshipping`

- **File**: `odoo/addons/stock_dropshipping/models/sale.py`
  - **Class**: `SaleOrder`
  - **Added Fields**: dropship_picking_count (_Integer_)
  - **Methods**:
    - `_compute_picking_ids (@depends)`
    - `action_view_delivery`
    - `action_view_dropship`
- **File**: `odoo/addons/stock_dropshipping/views/sale_order_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`view_order_form_inherit_sale_stock`](odoo/addons/stock_dropshipping/views/sale_order_views.xml#L4) -> `sale_stock.view_order_form_inherit_sale_stock`

### 📦 `website_event_booth_sale`

- **File**: `odoo/addons/website_event_booth_sale/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Methods**: `_cart_find_product_line`, `_verify_updated_quantity`, `_prepare_order_line_values`, `_prepare_order_line_update_values`

### 📦 `website_event_sale`

- **File**: `odoo/addons/website_event_sale/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Methods**: `_cart_find_product_line`, `_verify_updated_quantity`, `_prepare_order_line_values`, `_cart_update_order_line`, `_filter_can_send_abandoned_cart_mail`

### 📦 `website_sale`

- **File**: `odoo/addons/website_sale/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Added Fields**: website_id (_Many2one_), cart_recovery_email_sent (_Boolean_), shop_warning (_Char_), website_order_line (_One2many_), amount_delivery (_Monetary_), cart_quantity (_Integer_), only_services (_Boolean_), is_abandoned_cart (_Boolean_)
  - **Methods**:
    - `_compute_website_order_line (@depends)`
    - `_compute_amount_delivery (@depends)`
    - `_compute_cart_info (@depends)`
    - `_compute_abandoned_cart (@depends)`
    - `_compute_require_signature`
    - `_compute_payment_term_id`
    - `_compute_pricelist_id`
    - `_search_abandoned_cart`
    - `_compute_user_id`
    - `_default_team_id`
    - `create (@model_create_multi)`
    - `action_preview_sale_order`
    - `action_recovery_email_send`
    - `_get_cart_recovery_template`
    - `_get_non_delivery_lines`
    - `_get_amount_total_excluding_delivery`
    - `action_confirm`
    - `_send_payment_succeeded_for_order_mail`
    - `_get_note_url (@model)`
    - `_needs_customer_address`
    - `_update_address`
    - `_cart_add`
    - `_cart_find_product_line`
    - `_cart_update_line_quantity`
    - `_verify_updated_quantity`
    - `_cart_update_order_line`
    - `_prepare_order_line_update_values`
    - `_create_new_cart_line`
    - `_prepare_order_line_values`
    - `_check_combo_quantities`
    - `_verify_cart_after_update`
    - `_verify_cart`
    - `_cart_accessories`
    - `_cart_recovery_email_send`
    - `_message_mail_after_hook`
    - `_message_post_after_hook`
    - `_notify_get_recipients_groups`
    - `_is_reorder_allowed`
    - `_filter_can_send_abandoned_cart_mail`
    - `_has_deliverable_products`
    - `_remove_delivery_line`
    - `_get_preferred_delivery_method`
    - `_set_delivery_method`
    - `_get_delivery_methods`
    - `_is_anonymous_cart`
    - `_get_lang`
    - `_get_shop_warning`
    - `_is_cart_ready`
    - `_check_cart_is_ready_to_be_paid`
    - `_recompute_cart`
- **File**: `odoo/addons/website_sale/views/sale_order_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`view_sales_order_filter_ecommerce`](odoo/addons/website_sale/views/sale_order_views.xml#L3) -> `sale.view_sales_order_filter`
    - [`view_sales_order_filter_ecommerce_unpaid`](odoo/addons/website_sale/views/sale_order_views.xml#L26) -> `sale.view_sales_order_filter`
    - [`sale_order_view_form`](odoo/addons/website_sale/views/sale_order_views.xml#L153) -> `sale.view_order_form`
    - [`sale_order_tree`](odoo/addons/website_sale/views/sale_order_views.xml#L192) -> `sale.sale_order_tree`

### 📦 `website_sale_collect`

- **File**: `odoo/addons/website_sale_collect/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Methods**:
    - `_compute_warehouse_id`
    - `_compute_fiscal_position_id`
    - `_set_delivery_method`
    - `_set_pickup_location`
    - `_get_pickup_locations`
    - `_get_shop_warehouse_id`
    - `_check_cart_is_ready_to_be_paid`
    - `_prepare_in_store_default_location_data`
    - `_is_in_stock`
    - `_get_insufficient_stock_data`
    - `_verify_updated_quantity`

### 📦 `website_sale_gelato`

- **File**: `odoo/addons/website_sale_gelato/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Methods**: `_verify_updated_quantity`

### 📦 `website_sale_loyalty`

- **File**: `odoo/addons/website_sale_loyalty/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Added Fields**: disabled_auto_rewards (_Many2many_)
  - **Methods**:
    - `_get_program_domain`
    - `_get_trigger_domain`
    - `_get_program_timezone`
    - `_try_pending_coupon`
    - `_update_programs_and_rewards`
    - `_auto_apply_rewards`
    - `_compute_website_order_line`
    - `_compute_cart_info`
    - `get_promo_code_error`
    - `get_promo_code_success_message`
    - `_set_delivery_method`
    - `_remove_delivery_line`
    - `_cart_update_order_line`
    - `_verify_cart_after_update`
    - `_get_non_delivery_lines`
    - `_get_free_shipping_lines`
    - `_allow_nominative_programs`
    - `_gc_abandoned_coupons (@autovacuum)`
    - `_get_claimable_and_showable_rewards`
    - `_cart_find_product_line`
    - `_recompute_cart`

### 📦 `website_sale_mondialrelay`

- **File**: `odoo/addons/website_sale_mondialrelay/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Methods**: `_check_cart_is_ready_to_be_paid`, `_compute_partner_shipping_id`

### 📦 `website_sale_mrp`

- **File**: `odoo/addons/website_sale_mrp/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Methods**: `_get_unavailable_quantity_from_kits`

### 📦 `website_sale_slides`

- **File**: `odoo/addons/website_sale_slides/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Methods**: `_action_confirm`, `_verify_updated_quantity`

### 📦 `website_sale_stock`

- **File**: `odoo/addons/website_sale_stock/models/sale_order.py`
  - **Class**: `SaleOrder`
  - **Methods**:
    - `_compute_warehouse_id`
    - `_verify_updated_quantity`
    - `_get_cart_and_free_qty`
    - `_get_free_qty`
    - `_get_shop_warehouse_id`
    - `_get_cart_qty`
    - `_get_common_product_lines`
    - `_check_cart_is_ready_to_be_paid`
    - `_filter_can_send_abandoned_cart_mail`
    - `_all_product_available`

