# DecoNet : Scalable Netowrk architecture for Decoding dynamic decoding graphs


Please refer to our paper on arxiv : https://arxiv.org/abs/2301.08419

## Folder Structure

    .
    ├── design                  # Generic RTL files common to all configurations of Helios
    ├── test_benches            # Unit tests and other verification tests
    ├       ├── unit_tests      # Unit tests for RTL modules
    ├       ├── full_tests      # Test benches for various surface code parameters
    ├       └── test_data       # Input and expected outputs for full_tests
    ├── parameters              # Parameters shared by both design file and test benches
    └── software_code           # Scripts to generate sample inputs and outputs for verification

## Simulate DecoNet

Add the following files

```sh
add_files -fileset sim_1 -norecurse -scan_for_includes DecoNet/test_benches/full_tests/overall_verificaton_bench.sv
add_files -fileset sim_1 -norecurse -scan_for_includes {DecoNet/test_benches/full_tests/multi_fpga_verification_test_leaf.sv DecoNet/test_benches/full_tests/root_hub_test.sv}
add_files -fileset sim_1 -norecurse -scan_for_includes {DecoNet/design/generics/fifo_fwft.v DecoNet/design/stage_controller/root_hub_core.v}
add_files -fileset sim_1 -norecurse -scan_for_includes {DecoNet/design/channels/router.v DecoNet/design/stage_controller/control_node_root_FPGA.v}
add_files -fileset sim_1 -norecurse -scan_for_includes DecoNet/design/wrappers/Helios_single_FPGA_core.v
add_files -fileset sim_1 -norecurse -scan_for_includes {DecoNet/design/wrappers/single_FPGA_decoding_graph_dynamic_rsc.sv DecoNet/design/stage_controller/control_node_single_FPGA.v DecoNet/design/channels/message_handler.sv}
add_files -fileset sim_1 -norecurse -scan_for_includes DecoNet/design/pe/processing_unit_single_FPGA_v2.v
add_files -fileset sim_1 -norecurse -scan_for_includes {DecoNet/design/generics/tree_compare_solver.sv DecoNet/design/generics/ram.sv}
add_files -fileset sim_1 -norecurse -scan_for_includes DecoNet/design/pe/support_processing_unit.v
add_files -fileset sim_1 -norecurse -scan_for_includes DecoNet/design/channels/neighbor_link_internal_v2.v
```
    



