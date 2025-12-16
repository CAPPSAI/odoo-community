# Override Map: `stock.picking`

**Target Model**: `stock.picking`
**Active Modules**: 22
*(Localization modules `l10n_*` have been excluded)*

## 🔥 Hot Override Points (Global)

Methods overridden by the most modules (Top 15).

| Method | Override Count |
|---|---|
| `_action_done` | 3 |
| `_create_move_from_pos_order_lines` | 3 |
| `_send_confirmation_email` | 3 |
| `_get_possible_pickings_domain` | 2 |
| `_get_possible_batches_domain` | 2 |
| `_get_auto_batch_description` | 2 |
| `_is_auto_batchable` | 2 |
| `get_action_click_graph` | 2 |
| `_get_warehouse` | 2 |
| `_prepare_subcontract_mo_vals` | 2 |
| `_get_subcontract_mo_confirmation_ctx` | 2 |
| `_compute_is_dropship` | 2 |
| `_pre_action_done_hook` | 2 |
| `button_validate` | 2 |
| `write` | 2 |

## 🏗️ Core / Functional Overrides
_Modules that implement business logic (Stock, Sales, EDI, etc.)_

### 📦 `delivery_stock_picking_batch`

- **File**: `odoo/addons/delivery_stock_picking_batch/models/stock_picking.py`
  - **Class**: `StockPicking`
  - **Methods**: `_get_possible_pickings_domain`, `_get_possible_batches_domain`, `_get_auto_batch_description`, `_is_auto_batchable`

### 📦 `mrp`

- **File**: `odoo/addons/mrp/models/stock_picking.py`
  - **Class**: `StockPicking`
  - **Added Fields**: has_kits (_Boolean_), production_count (_Integer_), production_ids (_One2many_), production_group_id (_Many2one_)
  - **Methods**:
    - `_compute_has_kits (@depends)`
    - `_compute_mrp_production_ids (@depends)`
    - `action_detailed_operations`
    - `action_view_mrp_production`
    - `_less_quantities_than_expected_add_documents`
    - `get_action_click_graph (@model)`
- **File**: `odoo/addons/mrp/views/stock_picking_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`view_picking_form_inherit_mrp`](odoo/addons/mrp/views/stock_picking_views.xml#L109) -> `stock.view_picking_form`

### 📦 `mrp_subcontracting`

- **File**: `odoo/addons/mrp_subcontracting/models/stock_picking.py`
  - **Class**: `StockPicking`
  - **Added Fields**: show_subcontracting_details_visible (_Boolean_)
  - **Methods**:
    - `_compute_show_subcontracting_details_visible (@depends)`
    - `_compute_location_id (@depends)`
    - `_compute_show_lots_text (@depends)`
    - `_action_done`
    - `action_show_subcontract_details`
    - `_is_subcontract`
    - `_get_subcontract_production`
    - `_get_warehouse`
    - `_prepare_subcontract_mo_vals`
    - `_get_subcontract_mo_confirmation_ctx`
    - `_subcontracted_produce`
- **File**: `odoo/addons/mrp_subcontracting/views/stock_picking_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`stock_picking_form_view`](odoo/addons/mrp_subcontracting/views/stock_picking_views.xml#L3) -> `stock.view_picking_form`

### 📦 `mrp_subcontracting_dropshipping`

- **File**: `odoo/addons/mrp_subcontracting_dropshipping/models/stock_picking.py`
  - **Class**: `StockPicking`
  - **Methods**: `_compute_is_dropship`, `_get_warehouse`, `_prepare_subcontract_mo_vals`

### 📦 `mrp_subcontracting_purchase`

- **File**: `odoo/addons/mrp_subcontracting_purchase/models/stock_picking.py`
  - **Class**: `StockPicking`
  - **Added Fields**: subcontracting_source_purchase_count (_Integer_)
  - **Methods**:
    - `_compute_subcontracting_source_purchase_count (@depends)`
    - `action_view_subcontracting_source_purchase`
    - `_get_subcontracting_source_purchase`
    - `_get_subcontract_mo_confirmation_ctx`
- **File**: `odoo/addons/mrp_subcontracting_purchase/views/stock_picking_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`stock_picking_form_mrp_subcontracting`](odoo/addons/mrp_subcontracting_purchase/views/stock_picking_views.xml#L3) -> `stock.view_picking_form`

### 📦 `point_of_sale`

- **File**: `odoo/addons/point_of_sale/models/stock_picking.py`
  - **Class**: `StockPicking`
  - **Added Fields**: pos_session_id (_Many2one_), pos_order_id (_Many2one_)
  - **Methods**:
    - `_prepare_picking_vals`
    - `_create_picking_from_pos_order_lines (@model)`
    - `_prepare_stock_move_vals`
    - `_create_move_from_pos_order_lines`
    - `_link_owner_on_return_picking`
    - `_send_confirmation_email`

### 📦 `pos_repair`

- **File**: `odoo/addons/pos_repair/models/stock_picking.py`
  - **Class**: `StockPicking`
  - **Methods**: `_create_move_from_pos_order_lines`

### 📦 `pos_sale`

- **File**: `odoo/addons/pos_sale/models/stock_picking.py`
  - **Class**: `StockPicking`
  - **Methods**: `_create_move_from_pos_order_lines`

### 📦 `product_expiry`

- **File**: `odoo/addons/product_expiry/models/stock_picking.py`
  - **Class**: `StockPicking`
  - **Methods**: `_pre_action_done_hook`, `_check_expired_lots`, `_action_generate_expired_wizard`

### 📦 `project_stock`

- **File**: `odoo/addons/project_stock/models/stock_picking.py`
  - **Class**: `StockPicking`
  - **Added Fields**: project_id (_Many2one_)
- **File**: `odoo/addons/project_stock/views/stock_picking_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`view_picking_form_inherit_project_stock`](odoo/addons/project_stock/views/stock_picking_views.xml#L3) -> `stock.view_picking_form`

### 📦 `purchase_stock`

- **File**: `odoo/addons/purchase_stock/models/stock.py`
  - **Class**: `StockPicking`
  - **Added Fields**: purchase_id (_Many2one_), days_to_arrive (_Datetime_), delay_pass (_Datetime_)
  - **Methods**:
    - `_compute_effective_date (@depends)`
    - `_compute_date_order`
    - `_search_days_to_arrive (@model)`
    - `_search_delay_pass (@model)`
    - `_action_done`

### 📦 `repair`

- **File**: `odoo/addons/repair/models/stock_picking.py`
  - **Class**: `StockPicking`
  - **Added Fields**: repair_ids (_One2many_), nbr_repairs (_Integer_)
  - **Methods**:
    - `_compute_nbr_repairs (@depends)`
    - `action_repair_return`
    - `action_view_repairs`
    - `get_action_click_graph (@model)`
- **File**: `odoo/addons/repair/views/stock_picking_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`repair_view_picking_form`](odoo/addons/repair/views/stock_picking_views.xml#L33) -> `stock.view_picking_form`

### 📦 `sale_project_stock`

- **File**: `odoo/addons/sale_project_stock/models/stock_picking.py`
  - **Class**: `StockPicking`
  - **Methods**: `button_validate`

### 📦 `sale_stock`

- **File**: `odoo/addons/sale_stock/models/stock.py`
  - **Class**: `StockPicking`
  - **Added Fields**: sale_id (_Many2one_)
  - **Methods**:
    - `_compute_sale_id (@depends)`
    - `_compute_move_type (@depends)`
    - `_set_sale_id`
    - `_auto_init`
    - `_action_done`
    - `_log_less_quantities_than_expected`
    - `_can_return`
- **File**: `odoo/addons/sale_stock/views/stock_picking_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`view_picking_form`](odoo/addons/sale_stock/views/stock_picking_views.xml#L20) -> `stock.view_picking_form`

### 📦 `stock_account`

- **File**: `odoo/addons/stock_account/models/stock_picking.py`
  - **Class**: `StockPicking`
  - **Added Fields**: country_code (_Char_)
  - **Methods**:
    - `_check_backdate_allowed (@constrains)`
    - `_compute_is_date_editable`
    - `_is_date_in_lock_period`
- **File**: `odoo/addons/stock_account/views/stock_picking_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`view_picking_form`](odoo/addons/stock_account/views/stock_picking_views.xml#L3) -> `stock.view_picking_form`

### 📦 `stock_delivery`

- **File**: `odoo/addons/stock_delivery/models/stock_picking.py`
  - **Class**: `StockPicking`
  - **Added Fields**: carrier_price (_Float_), delivery_type (_Selection_), allowed_carrier_ids (_Many2many_), carrier_id (_Many2one_), weight (_Float_), carrier_tracking_ref (_Char_), carrier_tracking_url (_Char_), weight_uom_name (_Char_), is_return_picking (_Boolean_), return_label_ids (_One2many_), destination_country_code (_Char_), integration_level (_Selection_)
  - **Methods**:
    - `_get_default_weight_uom`
    - `_compute_weight_uom_name`
    - `_compute_allowed_carrier_ids (@depends)`
    - `_compute_carrier_tracking_url (@depends)`
    - `_compute_return_picking (@depends)`
    - `_compute_return_label`
    - `get_multiple_carrier_tracking`
    - `_cal_weight (@depends)`
    - `_carrier_exception_note`
    - `_send_confirmation_email`
    - `send_to_shipper`
    - `_check_carrier_details_compliance`
    - `print_return_label`
    - `_get_matching_delivery_lines`
    - `_prepare_sale_delivery_line_vals`
    - `_add_delivery_cost_to_so`
    - `open_website_url`
    - `cancel_shipment`
    - `_get_estimated_weight`
    - `_should_generate_commercial_invoice`
- **File**: `odoo/addons/stock_delivery/views/delivery_view.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`view_picking_withcarrier_out_form`](odoo/addons/stock_delivery/views/delivery_view.xml#L14) -> `stock.view_picking_form`
    - [`vpicktree_view_tree`](odoo/addons/stock_delivery/views/delivery_view.xml#L125) -> `stock.vpicktree`

### 📦 `stock_dropshipping`

- **File**: `odoo/addons/stock_dropshipping/models/stock.py`
  - **Class**: `StockPicking`
  - **Added Fields**: is_dropship (_Boolean_)
  - **Methods**:
    - `_compute_is_dropship (@depends)`
    - `_is_to_external_location`
- **File**: `odoo/addons/stock_dropshipping/views/stock_picking_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`view_picking_internal_search_inherit_stock_dropshipping`](odoo/addons/stock_dropshipping/views/stock_picking_views.xml#L3) -> `stock.view_picking_internal_search`

### 📦 `stock_fleet`

- **File**: `odoo/addons/stock_fleet/models/stock_picking.py`
  - **Class**: `StockPicking`
  - **Added Fields**: zip (_Char_)
  - **Methods**: `_search_zip`, `write`, `_reset_location`
- **File**: `odoo/addons/stock_fleet/views/stock_picking_view.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`vpicktree`](odoo/addons/stock_fleet/views/stock_picking_view.xml#L2) -> `stock.vpicktree`
    - [`stock_picking_tree_inherit_stock_fleet`](odoo/addons/stock_fleet/views/stock_picking_view.xml#L14) -> `stock_picking_batch.stock_picking_view_batch_tree_ref`

### 📦 `stock_picking_batch`

- **File**: `odoo/addons/stock_picking_batch/models/stock_picking.py`
  - **Class**: `StockPicking`
  - **Added Fields**: batch_id (_Many2one_), batch_sequence (_Integer_)
  - **Methods**:
    - `create (@model_create_multi)`
    - `write`
    - `action_add_operations`
    - `action_confirm`
    - `button_validate`
    - `_create_backorder`
    - `action_cancel`
    - `_should_show_transfers`
    - `_find_auto_batch`
    - `_is_auto_batchable`
    - `_get_possible_pickings_domain`
    - `_get_possible_batches_domain`
    - `_get_auto_batch_description`
    - `_is_single_transfer`
    - `_add_to_wave_post_picking_split_hook`
    - `assign_batch_user`
    - `action_view_batch`
- **File**: `odoo/addons/stock_picking_batch/views/stock_picking_batch_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`view_picking_form_inherited`](odoo/addons/stock_picking_batch/views/stock_picking_batch_views.xml#L3) -> `stock.view_picking_form`
    - [`view_picking_internal_search_inherit_stock_picking_batch`](odoo/addons/stock_picking_batch/views/stock_picking_batch_views.xml#L286) -> `stock.view_picking_internal_search`
- **File**: `odoo/addons/stock_picking_batch/views/stock_move_line_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`view_picking_internal_search_inherit`](odoo/addons/stock_picking_batch/views/stock_move_line_views.xml#L19) -> `stock.view_picking_internal_search`
- **File**: `odoo/addons/stock_picking_batch/views/stock_picking_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`stock_picking_form_inherit`](odoo/addons/stock_picking_batch/views/stock_picking_views.xml#L3) -> `stock.view_picking_form`
    - [`vpicktree`](odoo/addons/stock_picking_batch/views/stock_picking_views.xml#L24) -> `stock.vpicktree`
    - [`stock_picking_view_batch_tree_ref`](odoo/addons/stock_picking_batch/views/stock_picking_views.xml#L42) -> `stock.vpicktree`

### 📦 `stock_sms`

- **File**: `odoo/addons/stock_sms/models/stock_picking.py`
  - **Class**: `StockPicking`
  - **Methods**: `_pre_action_done_hook`, `_check_warn_sms`, `_action_generate_warn_sms_wizard`, `_send_confirmation_email`

### 📦 `website_sale_collect`

- **File**: `odoo/addons/website_sale_collect/views/stock_picking_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`stock_picking_form`](odoo/addons/website_sale_collect/views/stock_picking_views.xml#L3) -> `stock_delivery.view_picking_withcarrier_out_form`

### 📦 `website_sale_stock`

- **File**: `odoo/addons/website_sale_stock/models/stock_picking.py`
  - **Class**: `StockPicking`
  - **Added Fields**: website_id (_Many2one_)
- **File**: `odoo/addons/website_sale_stock/views/stock_picking_views.xml`
  - **Class**: `XML View Override`
  - **Modified Views**:
    - [`view_picking_form_inherit_website_sale_stock`](odoo/addons/website_sale_stock/views/stock_picking_views.xml#L3) -> `stock.view_picking_form`

