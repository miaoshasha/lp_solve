package(
    default_visibility = ["//visibility:public"],
)

cc_library(
    name = "lp_solve",
    srcs = [
        "bfp/bfp_LUSOL/lp_LUSOL.c",
        "bfp/bfp_LUSOL/LUSOL/lusol.c",
        "colamd/colamd.c",
        "fortify.c",
        "ini.c",
        "lp_Hash.c",
        "lp_MDO.c",
        "lp_MPS.c",
        "lp_SOS.c",
        "lp_crash.c",
        "lp_lib.c",
        "lp_matrix.c",
        "lp_mipbb.c",
        "lp_params.c",
        "lp_presolve.c",
        "lp_price.c",
        "lp_pricePSE.c",
        "lp_report.c",
        "lp_rlp.c",
        "lp_scale.c",
        "lp_simplex.c",
        "lp_utils.c",
        "lp_wlp.c",
        "shared/commonlib.c",
        "shared/mmio.c",
        "shared/myblas.c",
        "yacc_read.c",
    ]+glob([
        "bfp/bfp_LUSOL/LUSOL/*.c,",
    ]),
    hdrs = glob([
        "*.h,",
        "**/*.h",
        "bfp/bfp_LUSOL/LUSOL/*.c",
    ]) + [
        "bfp/lp_BFP1.c",
        "bfp/lp_BFP2.c",
    ],
    copts = [
        "-DYY_NEVER_INTERACTIVE",
        "-DPARSER_LP",
        "-DINVERSE_ACTIVE=INVERSE_LUSOL",
        "-DRoleIsExternalInvEngine",
    ],
    includes = [
        "./bfp",
        "./bfp/bfp_LUSOL",
        "./bfp/bfp_LUSOL/LUSOL",
        "./colamd",
        "./shared",
    ],
)

cc_binary(
    name = "lp_solve_main",
    srcs = ["lp_solve/lp_solve.c",],
    deps = [":lp_solve",],
)
