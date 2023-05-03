# SendingMail_UsingJava
<html lang="en" data-color-mode="auto" data-light-theme="light" data-dark-theme="dark" data-a11y-animated-images="system" data-turbo-loaded=""><script id="allow-copy_script">(function agent() {
    let unlock = false
    document.addEventListener('allow_copy', (event) => {
      unlock = event.detail.unlock
    })

    const copyEvents = [
      'copy',
      'cut',
      'contextmenu',
      'selectstart',
      'mousedown',
      'mouseup',
      'mousemove',
      'keydown',
      'keypress',
      'keyup',
    ]
    const rejectOtherHandlers = (e) => {
      if (unlock) {
        e.stopPropagation()
        if (e.stopImmediatePropagation) e.stopImmediatePropagation()
      }
    }
    copyEvents.forEach((evt) => {
      document.documentElement.addEventListener(evt, rejectOtherHandlers, {
        capture: true,
      })
    })
  })()</script><head><style type="text/css">.turbo-progress-bar {
  position: fixed;
  display: block;
  top: 0;
  left: 0;
  height: 3px;
  background: #0076ff;
  z-index: 2147483647;
  transition:
    width 300ms ease-out,
    opacity 150ms 150ms ease-in;
  transform: translate3d(0, 0, 0);
}
</style>
    <meta charset="utf-8">
  <link rel="dns-prefetch" href="https://github.githubassets.com">
  <link rel="dns-prefetch" href="https://avatars.githubusercontent.com">
  <link rel="dns-prefetch" href="https://github-cloud.s3.amazonaws.com">
  <link rel="dns-prefetch" href="https://user-images.githubusercontent.com/">
  <link rel="preconnect" href="https://github.githubassets.com" crossorigin="">
  <link rel="preconnect" href="https://avatars.githubusercontent.com">

  

  <link crossorigin="anonymous" media="all" rel="stylesheet" href="https://github.githubassets.com/assets/light-0946cdc16f15.css"><link crossorigin="anonymous" media="all" rel="stylesheet" href="https://github.githubassets.com/assets/dark-3946c959759a.css"><link data-color-theme="dark_dimmed" crossorigin="anonymous" media="all" rel="stylesheet" data-href="https://github.githubassets.com/assets/dark_dimmed-9b9a8c91acc5.css"><link data-color-theme="dark_high_contrast" crossorigin="anonymous" media="all" rel="stylesheet" data-href="https://github.githubassets.com/assets/dark_high_contrast-11302a585e33.css"><link data-color-theme="dark_colorblind" crossorigin="anonymous" media="all" rel="stylesheet" data-href="https://github.githubassets.com/assets/dark_colorblind-1a4564ab0fbf.css"><link data-color-theme="light_colorblind" crossorigin="anonymous" media="all" rel="stylesheet" data-href="https://github.githubassets.com/assets/light_colorblind-12a8b2aa9101.css"><link data-color-theme="light_high_contrast" crossorigin="anonymous" media="all" rel="stylesheet" data-href="https://github.githubassets.com/assets/light_high_contrast-5924a648f3e7.css"><link data-color-theme="light_tritanopia" crossorigin="anonymous" media="all" rel="stylesheet" data-href="https://github.githubassets.com/assets/light_tritanopia-05358496cb79.css"><link data-color-theme="dark_tritanopia" crossorigin="anonymous" media="all" rel="stylesheet" data-href="https://github.githubassets.com/assets/dark_tritanopia-aad6b801a158.css">
    <link crossorigin="anonymous" media="all" rel="stylesheet" href="https://github.githubassets.com/assets/primer-primitives-fb1d51d1ef66.css">
    <link crossorigin="anonymous" media="all" rel="stylesheet" href="https://github.githubassets.com/assets/primer-4d8f37cc9d91.css">
    <link crossorigin="anonymous" media="all" rel="stylesheet" href="https://github.githubassets.com/assets/global-243d3a393d7d.css">
    <link crossorigin="anonymous" media="all" rel="stylesheet" href="https://github.githubassets.com/assets/github-b717d68e0146.css">
  <link crossorigin="anonymous" media="all" rel="stylesheet" href="https://github.githubassets.com/assets/code-d9f97fd84f5d.css">

    <meta name="optimizely-datafile" content="{&quot;groups&quot;: [], &quot;environmentKey&quot;: &quot;production&quot;, &quot;rollouts&quot;: [], &quot;typedAudiences&quot;: [], &quot;projectId&quot;: &quot;16737760170&quot;, &quot;variables&quot;: [], &quot;featureFlags&quot;: [], &quot;experiments&quot;: [], &quot;version&quot;: &quot;4&quot;, &quot;audiences&quot;: [{&quot;conditions&quot;: &quot;[\&quot;or\&quot;, {\&quot;match\&quot;: \&quot;exact\&quot;, \&quot;name\&quot;: \&quot;$opt_dummy_attribute\&quot;, \&quot;type\&quot;: \&quot;custom_attribute\&quot;, \&quot;value\&quot;: \&quot;$opt_dummy_value\&quot;}]&quot;, &quot;id&quot;: &quot;$opt_dummy_audience&quot;, &quot;name&quot;: &quot;Optimizely-Generated Audience for Backwards Compatibility&quot;}], &quot;anonymizeIP&quot;: true, &quot;sdkKey&quot;: &quot;WTc6awnGuYDdG98CYRban&quot;, &quot;attributes&quot;: [{&quot;id&quot;: &quot;16822470375&quot;, &quot;key&quot;: &quot;user_id&quot;}, {&quot;id&quot;: &quot;17143601254&quot;, &quot;key&quot;: &quot;spammy&quot;}, {&quot;id&quot;: &quot;18175660309&quot;, &quot;key&quot;: &quot;organization_plan&quot;}, {&quot;id&quot;: &quot;18813001570&quot;, &quot;key&quot;: &quot;is_logged_in&quot;}, {&quot;id&quot;: &quot;19073851829&quot;, &quot;key&quot;: &quot;geo&quot;}, {&quot;id&quot;: &quot;20175462351&quot;, &quot;key&quot;: &quot;requestedCurrency&quot;}, {&quot;id&quot;: &quot;20785470195&quot;, &quot;key&quot;: &quot;country_code&quot;}, {&quot;id&quot;: &quot;21656311196&quot;, &quot;key&quot;: &quot;opened_downgrade_dialog&quot;}], &quot;botFiltering&quot;: false, &quot;accountId&quot;: &quot;16737760170&quot;, &quot;events&quot;: [{&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;17911811441&quot;, &quot;key&quot;: &quot;hydro_click.dashboard.teacher_toolbox_cta&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;18124116703&quot;, &quot;key&quot;: &quot;submit.organizations.complete_sign_up&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;18145892387&quot;, &quot;key&quot;: &quot;no_metric.tracked_outside_of_optimizely&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;18178755568&quot;, &quot;key&quot;: &quot;click.org_onboarding_checklist.add_repo&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;18180553241&quot;, &quot;key&quot;: &quot;submit.repository_imports.create&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;18186103728&quot;, &quot;key&quot;: &quot;click.help.learn_more_about_repository_creation&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;18188530140&quot;, &quot;key&quot;: &quot;test_event&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;18191963644&quot;, &quot;key&quot;: &quot;click.empty_org_repo_cta.transfer_repository&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;18195612788&quot;, &quot;key&quot;: &quot;click.empty_org_repo_cta.import_repository&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;18210945499&quot;, &quot;key&quot;: &quot;click.org_onboarding_checklist.invite_members&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;18211063248&quot;, &quot;key&quot;: &quot;click.empty_org_repo_cta.create_repository&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;18215721889&quot;, &quot;key&quot;: &quot;click.org_onboarding_checklist.update_profile&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;18224360785&quot;, &quot;key&quot;: &quot;click.org_onboarding_checklist.dismiss&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;18234832286&quot;, &quot;key&quot;: &quot;submit.organization_activation.complete&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;18252392383&quot;, &quot;key&quot;: &quot;submit.org_repository.create&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;18257551537&quot;, &quot;key&quot;: &quot;submit.org_member_invitation.create&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;18259522260&quot;, &quot;key&quot;: &quot;submit.organization_profile.update&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;18564603625&quot;, &quot;key&quot;: &quot;view.classroom_select_organization&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;18568612016&quot;, &quot;key&quot;: &quot;click.classroom_sign_in_click&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;18572592540&quot;, &quot;key&quot;: &quot;view.classroom_name&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;18574203855&quot;, &quot;key&quot;: &quot;click.classroom_create_organization&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;18582053415&quot;, &quot;key&quot;: &quot;click.classroom_select_organization&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;18589463420&quot;, &quot;key&quot;: &quot;click.classroom_create_classroom&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;18591323364&quot;, &quot;key&quot;: &quot;click.classroom_create_first_classroom&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;18591652321&quot;, &quot;key&quot;: &quot;click.classroom_grant_access&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;18607131425&quot;, &quot;key&quot;: &quot;view.classroom_creation&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;18831680583&quot;, &quot;key&quot;: &quot;upgrade_account_plan&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;19064064515&quot;, &quot;key&quot;: &quot;click.signup&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;19075373687&quot;, &quot;key&quot;: &quot;click.view_account_billing_page&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;19077355841&quot;, &quot;key&quot;: &quot;click.dismiss_signup_prompt&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;19079713938&quot;, &quot;key&quot;: &quot;click.contact_sales&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;19120963070&quot;, &quot;key&quot;: &quot;click.compare_account_plans&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;19151690317&quot;, &quot;key&quot;: &quot;click.upgrade_account_cta&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;19424193129&quot;, &quot;key&quot;: &quot;click.open_account_switcher&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;19520330825&quot;, &quot;key&quot;: &quot;click.visit_account_profile&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;19540970635&quot;, &quot;key&quot;: &quot;click.switch_account_context&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;19730198868&quot;, &quot;key&quot;: &quot;submit.homepage_signup&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;19820830627&quot;, &quot;key&quot;: &quot;click.homepage_signup&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;19988571001&quot;, &quot;key&quot;: &quot;click.create_enterprise_trial&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20036538294&quot;, &quot;key&quot;: &quot;click.create_organization_team&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20040653299&quot;, &quot;key&quot;: &quot;click.input_enterprise_trial_form&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20062030003&quot;, &quot;key&quot;: &quot;click.continue_with_team&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20068947153&quot;, &quot;key&quot;: &quot;click.create_organization_free&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20086636658&quot;, &quot;key&quot;: &quot;click.signup_continue.username&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20091648988&quot;, &quot;key&quot;: &quot;click.signup_continue.create_account&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20103637615&quot;, &quot;key&quot;: &quot;click.signup_continue.email&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20111574253&quot;, &quot;key&quot;: &quot;click.signup_continue.password&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20120044111&quot;, &quot;key&quot;: &quot;view.pricing_page&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20152062109&quot;, &quot;key&quot;: &quot;submit.create_account&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20165800992&quot;, &quot;key&quot;: &quot;submit.upgrade_payment_form&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20171520319&quot;, &quot;key&quot;: &quot;submit.create_organization&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20222645674&quot;, &quot;key&quot;: &quot;click.recommended_plan_in_signup.discuss_your_needs&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20227443657&quot;, &quot;key&quot;: &quot;submit.verify_primary_user_email&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20234607160&quot;, &quot;key&quot;: &quot;click.recommended_plan_in_signup.try_enterprise&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20238175784&quot;, &quot;key&quot;: &quot;click.recommended_plan_in_signup.team&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20239847212&quot;, &quot;key&quot;: &quot;click.recommended_plan_in_signup.continue_free&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20251097193&quot;, &quot;key&quot;: &quot;recommended_plan&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20438619534&quot;, &quot;key&quot;: &quot;click.pricing_calculator.1_member&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20456699683&quot;, &quot;key&quot;: &quot;click.pricing_calculator.15_members&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20467868331&quot;, &quot;key&quot;: &quot;click.pricing_calculator.10_members&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20476267432&quot;, &quot;key&quot;: &quot;click.trial_days_remaining&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20476357660&quot;, &quot;key&quot;: &quot;click.discover_feature&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20479287901&quot;, &quot;key&quot;: &quot;click.pricing_calculator.custom_members&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20481107083&quot;, &quot;key&quot;: &quot;click.recommended_plan_in_signup.apply_teacher_benefits&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20483089392&quot;, &quot;key&quot;: &quot;click.pricing_calculator.5_members&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20484283944&quot;, &quot;key&quot;: &quot;click.onboarding_task&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20484996281&quot;, &quot;key&quot;: &quot;click.recommended_plan_in_signup.apply_student_benefits&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20486713726&quot;, &quot;key&quot;: &quot;click.onboarding_task_breadcrumb&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20490791319&quot;, &quot;key&quot;: &quot;click.upgrade_to_enterprise&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20491786766&quot;, &quot;key&quot;: &quot;click.talk_to_us&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20494144087&quot;, &quot;key&quot;: &quot;click.dismiss_enterprise_trial&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20499722759&quot;, &quot;key&quot;: &quot;completed_all_tasks&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20500710104&quot;, &quot;key&quot;: &quot;completed_onboarding_tasks&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20513160672&quot;, &quot;key&quot;: &quot;click.read_doc&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20516196762&quot;, &quot;key&quot;: &quot;actions_enabled&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20518980986&quot;, &quot;key&quot;: &quot;click.dismiss_trial_banner&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20535446721&quot;, &quot;key&quot;: &quot;click.issue_actions_prompt.dismiss_prompt&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20557002247&quot;, &quot;key&quot;: &quot;click.issue_actions_prompt.setup_workflow&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20595070227&quot;, &quot;key&quot;: &quot;click.pull_request_setup_workflow&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20626600314&quot;, &quot;key&quot;: &quot;click.seats_input&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20642310305&quot;, &quot;key&quot;: &quot;click.decrease_seats_number&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20662990045&quot;, &quot;key&quot;: &quot;click.increase_seats_number&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20679620969&quot;, &quot;key&quot;: &quot;click.public_product_roadmap&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20761240940&quot;, &quot;key&quot;: &quot;click.dismiss_survey_banner&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20767210721&quot;, &quot;key&quot;: &quot;click.take_survey&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20795281201&quot;, &quot;key&quot;: &quot;click.archive_list&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20966790249&quot;, &quot;key&quot;: &quot;contact_sales.submit&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20996500333&quot;, &quot;key&quot;: &quot;contact_sales.existing_customer&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;20996890162&quot;, &quot;key&quot;: &quot;contact_sales.blank_message_field&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;21000470317&quot;, &quot;key&quot;: &quot;contact_sales.personal_email&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;21002790172&quot;, &quot;key&quot;: &quot;contact_sales.blank_phone_field&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;21354412592&quot;, &quot;key&quot;: &quot;click.dismiss_create_readme&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;21366102546&quot;, &quot;key&quot;: &quot;click.dismiss_zero_user_content&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;21370252505&quot;, &quot;key&quot;: &quot;account_did_downgrade&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;21370840408&quot;, &quot;key&quot;: &quot;click.cta_create_readme&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;21375451068&quot;, &quot;key&quot;: &quot;click.cta_create_new_repository&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;21385390948&quot;, &quot;key&quot;: &quot;click.zero_user_content&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;21467712175&quot;, &quot;key&quot;: &quot;click.downgrade_keep&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;21484112202&quot;, &quot;key&quot;: &quot;click.downgrade&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;21495292213&quot;, &quot;key&quot;: &quot;click.downgrade_survey_exit&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;21508241468&quot;, &quot;key&quot;: &quot;click.downgrade_survey_submit&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;21512030356&quot;, &quot;key&quot;: &quot;click.downgrade_support&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;21539090022&quot;, &quot;key&quot;: &quot;click.downgrade_exit&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;21543640644&quot;, &quot;key&quot;: &quot;click_fetch_upstream&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;21646510300&quot;, &quot;key&quot;: &quot;click.move_your_work&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;21656151116&quot;, &quot;key&quot;: &quot;click.add_branch_protection_rule&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;21663860599&quot;, &quot;key&quot;: &quot;click.downgrade_dialog_open&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;21687860483&quot;, &quot;key&quot;: &quot;click.learn_about_protected_branches&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;21689050333&quot;, &quot;key&quot;: &quot;click.dismiss_protect_this_branch&quot;}, {&quot;experimentIds&quot;: [], &quot;id&quot;: &quot;21864370109&quot;, &quot;key&quot;: &quot;click.sign_in&quot;}], &quot;revision&quot;: &quot;1372&quot;}">


  <script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/wp-runtime-827ced82090f.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/vendors-node_modules_stacktrace-parser_dist_stack-trace-parser_esm_js-node_modules_github_bro-a4c183-ae93d3fba59c.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/ui_packages_failbot_failbot_ts-e38c93eab86e.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/environment-de3997b81651.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/vendors-node_modules_github_selector-observer_dist_index_esm_js-2646a2c533e3.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/vendors-node_modules_github_relative-time-element_dist_index_js-99e288659d4f.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/vendors-node_modules_fzy_js_index_js-node_modules_github_markdown-toolbar-element_dist_index_js-e3de700a4c9d.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/vendors-node_modules_delegated-events_dist_index_js-node_modules_github_auto-complete-element-5b3870-ff38694180c6.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/vendors-node_modules_github_file-attachment-element_dist_index_js-node_modules_github_text-ex-3415a8-7ecc10fb88d0.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/vendors-node_modules_github_filter-input-element_dist_index_js-node_modules_github_remote-inp-8873b7-5771678648e0.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/vendors-node_modules_primer_view-components_app_components_primer_primer_js-node_modules_gith-3af896-2189f4f604ee.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/github-elements-7b037525f59f.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/element-registry-298a91af1d4e.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/vendors-node_modules_lit-html_lit-html_js-9d9fe1859ce5.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/vendors-node_modules_github_mini-throttle_dist_index_js-node_modules_github_alive-client_dist-bf5aa2-424aa982deef.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/vendors-node_modules_github_turbo_dist_turbo_es2017-esm_js-ba0e4d5b3207.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/vendors-node_modules_primer_behaviors_dist_esm_dimensions_js-node_modules_github_hotkey_dist_-269f6d-5d145c7cc849.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/vendors-node_modules_github_remote-form_dist_index_js-node_modules_scroll-anchoring_dist_scro-5881a7-44d01ee9e782.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/vendors-node_modules_color-convert_index_js-35b3ae68c408.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/vendors-node_modules_github_paste-markdown_dist_index_esm_js-node_modules_github_quote-select-973149-7c1c1618332f.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/app_assets_modules_github_updatable-content_ts-dadb69f79923.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/app_assets_modules_github_behaviors_keyboard-shortcuts-helper_ts-app_assets_modules_github_be-f5afdb-3f05df4c282b.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/app_assets_modules_github_blob-anchor_ts-app_assets_modules_github_code-editor_ts-app_assets_-d384d0-c22babf4e371.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/app_assets_modules_github_sticky-scroll-into-view_ts-1d145b63ed56.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/app_assets_modules_github_behaviors_ajax-error_ts-app_assets_modules_github_behaviors_include-2e2258-dae7d38e0248.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/app_assets_modules_github_behaviors_commenting_edit_ts-app_assets_modules_github_behaviors_ht-83c235-80a9915bf75c.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/behaviors-724e12423b4d.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/vendors-node_modules_delegated-events_dist_index_js-node_modules_github_catalyst_lib_index_js-623425af41e1.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/notifications-global-4dc6f295cc92.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/vendors-node_modules_optimizely_optimizely-sdk_dist_optimizely_browser_es_min_js-node_modules-089adc-2328ba323205.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/optimizely-1c55a525615e.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/vendors-node_modules_virtualized-list_es_index_js-node_modules_github_template-parts_lib_index_js-c3e624db1d89.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/vendors-node_modules_github_mini-throttle_dist_decorators_js-node_modules_github_remote-form_-e3de2b-93bbe15e6e78.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/vendors-node_modules_github_file-attachment-element_dist_index_js-node_modules_github_filter--b2311f-939ba5085db0.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/app_assets_modules_github_ref-selector_ts-8f8b76ecd8d3.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/repositories-1d1e8eb62b9d.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/vendors-node_modules_github_clipboard-copy-element_dist_index_esm_js-node_modules_scroll-anch-c93c97-d63d35dd5d0b.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/app_assets_modules_github_diffs_blob-lines_ts-app_assets_modules_github_diffs_linkable-line-n-f96c66-3aec21e0f76c.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/diffs-8f94880ed060.js"></script>
  

  <title>simple-java-mail/README.md at master · bbottema/simple-java-mail</title>



  <meta name="route-pattern" content="/:user_id/:repository/blob/*name(/*path)">

    
  <meta name="current-catalog-service-hash" content="581425c0eaaa5e5e53c5b736f58a14dbe5d38b0be425901738ad0670bd1d5a33">


  <meta name="request-id" content="F9CA:7272:1FF8DDF:24DE7A2:64523824" data-turbo-transient="true"><meta name="html-safe-nonce" content="848efb8dfb6e58078f703daa93388c5abdde93bbe86c6f51f4d266cb3a1343b9" data-turbo-transient="true"><meta name="visitor-payload" content="eyJyZWZlcnJlciI6Imh0dHBzOi8vd3d3Lmdvb2dsZS5jb20vIiwicmVxdWVzdF9pZCI6IkY5Q0E6NzI3MjoxRkY4RERGOjI0REU3QTI6NjQ1MjM4MjQiLCJ2aXNpdG9yX2lkIjoiMTg2ODA0OTk3NjQzODQ0Mzg2NiIsInJlZ2lvbl9lZGdlIjoiY2VudHJhbGluZGlhIiwicmVnaW9uX3JlbmRlciI6ImlhZCJ9" data-turbo-transient="true"><meta name="visitor-hmac" content="174d196c839df97dfdd48c33836788804f7c581eb11baed1a31383f153d586d5" data-turbo-transient="true">


    <meta name="hovercard-subject-tag" content="repository:34100441" data-turbo-transient="">


  <meta name="github-keyboard-shortcuts" content="repository,source-code,file-tree" data-turbo-transient="true">
  

  <meta name="selected-link" value="repo_source" data-turbo-transient="">

    <meta name="google-site-verification" content="c1kuD-K2HIVF635lypcsWPoD4kilo5-jA_wBFyT4uMY">
  <meta name="google-site-verification" content="KT5gs8h0wvaagLKAVWq8bbeNwnZZK1r1XQysX3xurLU">
  <meta name="google-site-verification" content="ZzhVyEFwb7w3e0-uOTltm8Jsck2F5StVihD0exw2fsA">
  <meta name="google-site-verification" content="GXs5KoUUkNCoaAZn7wPN-t01Pywp9M3sEjnt_3_ZWPc">
  <meta name="google-site-verification" content="Apib7-x98H0j5cPqHWwSMm6dNU4GmODRoqxLiDzdx9I">

<meta name="octolytics-url" content="https://collector.github.com/github/collect"><meta name="octolytics-actor-id" content="99464989"><meta name="octolytics-actor-login" content="S230306"><meta name="octolytics-actor-hash" content="afd3914ef7f3d709b15aabead75b3df77a8b9bb965262fb4dd64c47373cf5fe4">

  <meta name="analytics-location" content="/<user-name>/<repo-name>/blob/show" data-turbo-transient="true">

  




  

    <meta name="user-login" content="S230306">

  <link rel="sudo-modal" href="/sessions/sudo_modal">

    <meta name="viewport" content="width=device-width">
    
      <meta name="description" content="Simple API, Complex Emails (Jakarta Mail smtp wrapper) - simple-java-mail/README.md at master · bbottema/simple-java-mail">
      <link rel="search" type="application/opensearchdescription+xml" href="/opensearch.xml" title="GitHub">
    <link rel="fluid-icon" href="https://github.com/fluidicon.png" title="GitHub">
    <meta property="fb:app_id" content="1401488693436528">
    <meta name="apple-itunes-app" content="app-id=1477376905">
      <meta name="twitter:image:src" content="https://opengraph.githubassets.com/c39568ff9f986edec9abff9ad5896f3897f881fc8be1dd3759bb0a67573cca32/bbottema/simple-java-mail"><meta name="twitter:site" content="@github"><meta name="twitter:card" content="summary_large_image"><meta name="twitter:title" content="simple-java-mail/README.md at master · bbottema/simple-java-mail"><meta name="twitter:description" content="Simple API, Complex Emails (Jakarta Mail smtp wrapper) - simple-java-mail/README.md at master · bbottema/simple-java-mail">
      <meta property="og:image" content="https://opengraph.githubassets.com/c39568ff9f986edec9abff9ad5896f3897f881fc8be1dd3759bb0a67573cca32/bbottema/simple-java-mail"><meta property="og:image:alt" content="Simple API, Complex Emails (Jakarta Mail smtp wrapper) - simple-java-mail/README.md at master · bbottema/simple-java-mail"><meta property="og:image:width" content="1200"><meta property="og:image:height" content="600"><meta property="og:site_name" content="GitHub"><meta property="og:type" content="object"><meta property="og:title" content="simple-java-mail/README.md at master · bbottema/simple-java-mail"><meta property="og:url" content="https://github.com/bbottema/simple-java-mail"><meta property="og:description" content="Simple API, Complex Emails (Jakarta Mail smtp wrapper) - simple-java-mail/README.md at master · bbottema/simple-java-mail">
      
    <link rel="assets" href="https://github.githubassets.com/">
      <link rel="shared-web-socket" href="wss://alive.github.com/_sockets/u/99464989/ws?session=eyJ2IjoiVjMiLCJ1Ijo5OTQ2NDk4OSwicyI6MTEwNjQyMTg2MCwiYyI6NDU2MTgxNTEwLCJ0IjoxNjgzMTA5OTI2fQ==--088878fc5330110f7d766d24429b716a10600018a3d393cb47933dc1a4247eca" data-refresh-url="/_alive" data-session-id="d126db0ac7663ff4e3c8c9afd37afc5f58ccec996ccee69dc8bfe64ed577addd">
      <link rel="shared-web-socket-src" href="/assets-cdn/worker/socket-worker-71e98f781d79.js">


        <meta name="hostname" content="github.com">


      <meta name="keyboard-shortcuts-preference" content="all">

        <meta name="expected-hostname" content="github.com">

    <meta name="enabled-features" content="TURBO_EXPERIMENT_RISKY,IMAGE_METRIC_TRACKING,GEOJSON_AZURE_MAPS">


  <meta http-equiv="x-pjax-version" content="11fb3c8fd435116656da532d468d73ba081808cd72089030ddb42c1bde7329e2" data-turbo-track="reload">
  <meta http-equiv="x-pjax-csp-version" content="0db263f9a873141d8256f783c35f244c06d490aacc3b680f99794dd8fd59fb59" data-turbo-track="reload">
  <meta http-equiv="x-pjax-css-version" content="d0d1f5be9d5737dd36dc184b20f007cd603f64dae470c6d16fbee094e3cf2c43" data-turbo-track="reload">
  <meta http-equiv="x-pjax-js-version" content="d33297569cfb9d022cd4e9fe23418d4c759f80896b53d3261e3d3ffefd2a71fc" data-turbo-track="reload">

  <meta name="turbo-cache-control" content="no-preview" data-turbo-transient="">

        <meta data-hydrostats="publish">

  <meta name="go-import" content="github.com/bbottema/simple-java-mail git https://github.com/bbottema/simple-java-mail.git">

  <meta name="octolytics-dimension-user_id" content="2115718"><meta name="octolytics-dimension-user_login" content="bbottema"><meta name="octolytics-dimension-repository_id" content="34100441"><meta name="octolytics-dimension-repository_nwo" content="bbottema/simple-java-mail"><meta name="octolytics-dimension-repository_public" content="true"><meta name="octolytics-dimension-repository_is_fork" content="false"><meta name="octolytics-dimension-repository_network_root_id" content="34100441"><meta name="octolytics-dimension-repository_network_root_nwo" content="bbottema/simple-java-mail">



    <link rel="canonical" href="https://github.com/bbottema/simple-java-mail/blob/master/README.md" data-turbo-transient="">
  <meta name="turbo-body-classes" content="logged-in env-production page-responsive page-blob">


  <meta name="browser-stats-url" content="https://api.github.com/_private/browser/stats">

  <meta name="browser-errors-url" content="https://api.github.com/_private/browser/errors">

  <meta name="browser-optimizely-client-errors-url" content="https://api.github.com/_private/browser/optimizely_client/errors">

  <link rel="mask-icon" href="https://github.githubassets.com/pinned-octocat.svg" color="#000000">
  <link rel="alternate icon" class="js-site-favicon" type="image/png" href="https://github.githubassets.com/favicons/favicon.png">
  <link rel="icon" class="js-site-favicon" type="image/svg+xml" href="https://github.githubassets.com/favicons/favicon.svg">

<meta name="theme-color" content="#1e2327">
<meta name="color-scheme" content="light dark">


  <link rel="manifest" href="/manifest.json" crossorigin="use-credentials">

  <link rel="prefetch"><style>.ant-avatar{box-sizing:border-box;margin:0;padding:0;color:rgba(0,0,0,.85);font-size:14px;font-variant:tabular-nums;line-height:1.5715;list-style:none;font-feature-settings:"tnum";position:relative;display:inline-block;overflow:hidden;color:#fff;white-space:nowrap;text-align:center;vertical-align:middle;background:#ccc;width:32px;height:32px;line-height:32px;border-radius:50%}.ant-avatar-image{background:rgba(0,0,0,0)}.ant-avatar .ant-image-img{display:block}.ant-avatar-string{position:absolute;left:50%;transform-origin:0 center}.ant-avatar.ant-avatar-icon{font-size:18px}.ant-avatar.ant-avatar-icon>.anticon{margin:0}.ant-avatar-lg{width:40px;height:40px;line-height:40px;border-radius:50%}.ant-avatar-lg-string{position:absolute;left:50%;transform-origin:0 center}.ant-avatar-lg.ant-avatar-icon{font-size:24px}.ant-avatar-lg.ant-avatar-icon>.anticon{margin:0}.ant-avatar-sm{width:24px;height:24px;line-height:24px;border-radius:50%}.ant-avatar-sm-string{position:absolute;left:50%;transform-origin:0 center}.ant-avatar-sm.ant-avatar-icon{font-size:14px}.ant-avatar-sm.ant-avatar-icon>.anticon{margin:0}.ant-avatar-square{border-radius:2px}.ant-avatar>img{display:block;width:100%;height:100%;-o-object-fit:cover;object-fit:cover}.ant-avatar-group{display:inline-flex}.ant-avatar-group .ant-avatar{border:1px solid #fff}.ant-avatar-group .ant-avatar:not(:first-child){margin-left:-8px}.ant-avatar-group-popover .ant-avatar+.ant-avatar{margin-left:3px}.ant-avatar-group-rtl .ant-avatar:not(:first-child){margin-right:-8px;margin-left:0}.ant-avatar-group-popover.ant-popover-rtl .ant-avatar+.ant-avatar{margin-right:3px;margin-left:0}</style><style>.ant-badge{box-sizing:border-box;margin:0;padding:0;color:rgba(0,0,0,.85);font-size:14px;font-variant:tabular-nums;line-height:1.5715;list-style:none;font-feature-settings:"tnum";position:relative;display:inline-block;line-height:1}.ant-badge-count{z-index:auto;min-width:20px;height:20px;padding:0 6px;color:#fff;font-weight:normal;font-size:12px;line-height:20px;white-space:nowrap;text-align:center;background:#ff4d4f;border-radius:10px;box-shadow:0 0 0 1px #fff}.ant-badge-count a,.ant-badge-count a:hover{color:#fff}.ant-badge-count-sm{min-width:14px;height:14px;padding:0;font-size:12px;line-height:14px;border-radius:7px}.ant-badge-multiple-words{padding:0 8px}.ant-badge-dot{z-index:auto;width:6px;min-width:6px;height:6px;background:#ff4d4f;border-radius:100%;box-shadow:0 0 0 1px #fff}.ant-badge-dot.ant-scroll-number{transition:background 1.5s}.ant-badge-count,.ant-badge-dot,.ant-badge .ant-scroll-number-custom-component{position:absolute;top:0;right:0;transform:translate(50%, -50%);transform-origin:100% 0%}.ant-badge-count.anticon-spin,.ant-badge-dot.anticon-spin,.ant-badge .ant-scroll-number-custom-component.anticon-spin{animation:antBadgeLoadingCircle 1s infinite linear}.ant-badge-status{line-height:inherit;vertical-align:baseline}.ant-badge-status-dot{position:relative;top:-1px;display:inline-block;width:6px;height:6px;vertical-align:middle;border-radius:50%}.ant-badge-status-success{background-color:#52c41a}.ant-badge-status-processing{position:relative;background-color:#1890ff}.ant-badge-status-processing::after{position:absolute;top:0;left:0;width:100%;height:100%;border:1px solid #1890ff;border-radius:50%;animation:antStatusProcessing 1.2s infinite ease-in-out;content:""}.ant-badge-status-default{background-color:#d9d9d9}.ant-badge-status-error{background-color:#ff4d4f}.ant-badge-status-warning{background-color:#faad14}.ant-badge-status-pink{background:#eb2f96}.ant-badge-status-magenta{background:#eb2f96}.ant-badge-status-red{background:#f5222d}.ant-badge-status-volcano{background:#fa541c}.ant-badge-status-orange{background:#fa8c16}.ant-badge-status-yellow{background:#fadb14}.ant-badge-status-gold{background:#faad14}.ant-badge-status-cyan{background:#13c2c2}.ant-badge-status-lime{background:#a0d911}.ant-badge-status-green{background:#52c41a}.ant-badge-status-blue{background:#1890ff}.ant-badge-status-geekblue{background:#2f54eb}.ant-badge-status-purple{background:#722ed1}.ant-badge-status-text{margin-left:8px;color:rgba(0,0,0,.85);font-size:14px}.ant-badge-zoom-appear,.ant-badge-zoom-enter{animation:antZoomBadgeIn .3s cubic-bezier(0.12, 0.4, 0.29, 1.46);animation-fill-mode:both}.ant-badge-zoom-leave{animation:antZoomBadgeOut .3s cubic-bezier(0.71, -0.46, 0.88, 0.6);animation-fill-mode:both}.ant-badge-not-a-wrapper .ant-badge-zoom-appear,.ant-badge-not-a-wrapper .ant-badge-zoom-enter{animation:antNoWrapperZoomBadgeIn .3s cubic-bezier(0.12, 0.4, 0.29, 1.46)}.ant-badge-not-a-wrapper .ant-badge-zoom-leave{animation:antNoWrapperZoomBadgeOut .3s cubic-bezier(0.71, -0.46, 0.88, 0.6)}.ant-badge-not-a-wrapper:not(.ant-badge-status){vertical-align:middle}.ant-badge-not-a-wrapper .ant-scroll-number-custom-component,.ant-badge-not-a-wrapper .ant-badge-count{transform:none}.ant-badge-not-a-wrapper .ant-scroll-number-custom-component,.ant-badge-not-a-wrapper .ant-scroll-number{position:relative;top:auto;display:block;transform-origin:50% 50%}@keyframes antStatusProcessing{0%{transform:scale(0.8);opacity:.5}100%{transform:scale(2.4);opacity:0}}.ant-scroll-number{overflow:hidden;direction:ltr}.ant-scroll-number-only{position:relative;display:inline-block;height:20px;transition:all .3s cubic-bezier(0.645, 0.045, 0.355, 1);-webkit-transform-style:preserve-3d;-webkit-backface-visibility:hidden}.ant-scroll-number-only>p.ant-scroll-number-only-unit{height:20px;margin:0;-webkit-transform-style:preserve-3d;-webkit-backface-visibility:hidden}.ant-scroll-number-symbol{vertical-align:top}@keyframes antZoomBadgeIn{0%{transform:scale(0) translate(50%, -50%);opacity:0}100%{transform:scale(1) translate(50%, -50%)}}@keyframes antZoomBadgeOut{0%{transform:scale(1) translate(50%, -50%)}100%{transform:scale(0) translate(50%, -50%);opacity:0}}@keyframes antNoWrapperZoomBadgeIn{0%{transform:scale(0);opacity:0}100%{transform:scale(1)}}@keyframes antNoWrapperZoomBadgeOut{0%{transform:scale(1)}100%{transform:scale(0);opacity:0}}@keyframes antBadgeLoadingCircle{0%{transform-origin:50%}100%{transform:translate(50%, -50%) rotate(360deg);transform-origin:50%}}.ant-ribbon-wrapper{position:relative}.ant-ribbon{box-sizing:border-box;margin:0;padding:0;color:rgba(0,0,0,.85);font-size:14px;font-variant:tabular-nums;line-height:1.5715;list-style:none;font-feature-settings:"tnum";position:absolute;top:8px;height:22px;padding:0 8px;color:#fff;line-height:22px;white-space:nowrap;background-color:#1890ff;border-radius:2px}.ant-ribbon-text{color:#fff}.ant-ribbon-corner{position:absolute;top:100%;width:8px;height:8px;color:currentcolor;border:4px solid;transform:scaleY(0.75);transform-origin:top}.ant-ribbon-corner::after{position:absolute;top:-4px;left:-4px;width:inherit;height:inherit;color:rgba(0,0,0,.25);border:inherit;content:""}.ant-ribbon-color-pink{color:#eb2f96;background:#eb2f96}.ant-ribbon-color-magenta{color:#eb2f96;background:#eb2f96}.ant-ribbon-color-red{color:#f5222d;background:#f5222d}.ant-ribbon-color-volcano{color:#fa541c;background:#fa541c}.ant-ribbon-color-orange{color:#fa8c16;background:#fa8c16}.ant-ribbon-color-yellow{color:#fadb14;background:#fadb14}.ant-ribbon-color-gold{color:#faad14;background:#faad14}.ant-ribbon-color-cyan{color:#13c2c2;background:#13c2c2}.ant-ribbon-color-lime{color:#a0d911;background:#a0d911}.ant-ribbon-color-green{color:#52c41a;background:#52c41a}.ant-ribbon-color-blue{color:#1890ff;background:#1890ff}.ant-ribbon-color-geekblue{color:#2f54eb;background:#2f54eb}.ant-ribbon-color-purple{color:#722ed1;background:#722ed1}.ant-ribbon.ant-ribbon-placement-end{right:-8px;border-bottom-right-radius:0}.ant-ribbon.ant-ribbon-placement-end .ant-ribbon-corner{right:0;border-color:currentcolor rgba(0,0,0,0) rgba(0,0,0,0) currentcolor}.ant-ribbon.ant-ribbon-placement-start{left:-8px;border-bottom-left-radius:0}.ant-ribbon.ant-ribbon-placement-start .ant-ribbon-corner{left:0;border-color:currentcolor currentcolor rgba(0,0,0,0) rgba(0,0,0,0)}.ant-badge-rtl{direction:rtl}.ant-badge-rtl.ant-badge:not(.ant-badge-not-a-wrapper) .ant-badge-count,.ant-badge-rtl.ant-badge:not(.ant-badge-not-a-wrapper) .ant-badge-dot,.ant-badge-rtl.ant-badge:not(.ant-badge-not-a-wrapper) .ant-scroll-number-custom-component{right:auto;left:0;direction:ltr;transform:translate(-50%, -50%);transform-origin:0% 0%}.ant-badge-rtl.ant-badge:not(.ant-badge-not-a-wrapper) .ant-scroll-number-custom-component{right:auto;left:0;transform:translate(-50%, -50%);transform-origin:0% 0%}.ant-badge-rtl .ant-badge-status-text{margin-right:8px;margin-left:0}.ant-badge:not(.ant-badge-not-a-wrapper).ant-badge-rtl .ant-badge-zoom-appear,.ant-badge:not(.ant-badge-not-a-wrapper).ant-badge-rtl .ant-badge-zoom-enter{animation-name:antZoomBadgeInRtl}.ant-badge:not(.ant-badge-not-a-wrapper).ant-badge-rtl .ant-badge-zoom-leave{animation-name:antZoomBadgeOutRtl}.ant-ribbon-rtl{direction:rtl}.ant-ribbon-rtl.ant-ribbon-placement-end{right:unset;left:-8px;border-bottom-right-radius:2px;border-bottom-left-radius:0}.ant-ribbon-rtl.ant-ribbon-placement-end .ant-ribbon-corner{right:unset;left:0;border-color:currentcolor currentcolor rgba(0,0,0,0) rgba(0,0,0,0)}.ant-ribbon-rtl.ant-ribbon-placement-end .ant-ribbon-corner::after{border-color:currentcolor currentcolor rgba(0,0,0,0) rgba(0,0,0,0)}.ant-ribbon-rtl.ant-ribbon-placement-start{right:-8px;left:unset;border-bottom-right-radius:0;border-bottom-left-radius:2px}.ant-ribbon-rtl.ant-ribbon-placement-start .ant-ribbon-corner{right:0;left:unset;border-color:currentcolor rgba(0,0,0,0) rgba(0,0,0,0) currentcolor}.ant-ribbon-rtl.ant-ribbon-placement-start .ant-ribbon-corner::after{border-color:currentcolor rgba(0,0,0,0) rgba(0,0,0,0) currentcolor}@keyframes antZoomBadgeInRtl{0%{transform:scale(0) translate(-50%, -50%);opacity:0}100%{transform:scale(1) translate(-50%, -50%)}}@keyframes antZoomBadgeOutRtl{0%{transform:scale(1) translate(-50%, -50%)}100%{transform:scale(0) translate(-50%, -50%);opacity:0}}</style><style>.ant-btn{line-height:1.5715;position:relative;display:inline-block;font-weight:400;white-space:nowrap;text-align:center;background-image:none;border:1px solid rgba(0,0,0,0);box-shadow:0 2px 0 rgba(0,0,0,.015);cursor:pointer;transition:all .3s cubic-bezier(0.645, 0.045, 0.355, 1);-webkit-user-select:none;-moz-user-select:none;-ms-user-select:none;user-select:none;touch-action:manipulation;height:32px;padding:4px 15px;font-size:14px;border-radius:2px;color:rgba(0,0,0,.85);border-color:#d9d9d9;background:#fff}.ant-btn>.anticon{line-height:1}.ant-btn,.ant-btn:active,.ant-btn:focus{outline:0}.ant-btn:not([disabled]):hover{text-decoration:none}.ant-btn:not([disabled]):active{outline:0;box-shadow:none}.ant-btn[disabled]{cursor:not-allowed}.ant-btn[disabled]>*{pointer-events:none}.ant-btn-lg{height:40px;padding:6.4px 15px;font-size:16px;border-radius:2px}.ant-btn-sm{height:24px;padding:0px 7px;font-size:14px;border-radius:2px}.ant-btn>a:only-child{color:currentcolor}.ant-btn>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn:hover,.ant-btn:focus{color:#40a9ff;border-color:#40a9ff;background:#fff}.ant-btn:hover>a:only-child,.ant-btn:focus>a:only-child{color:currentcolor}.ant-btn:hover>a:only-child::after,.ant-btn:focus>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn:active{color:#096dd9;border-color:#096dd9;background:#fff}.ant-btn:active>a:only-child{color:currentcolor}.ant-btn:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn[disabled],.ant-btn[disabled]:hover,.ant-btn[disabled]:focus,.ant-btn[disabled]:active{color:rgba(0,0,0,.25);border-color:#d9d9d9;background:#f5f5f5;text-shadow:none;box-shadow:none}.ant-btn[disabled]>a:only-child,.ant-btn[disabled]:hover>a:only-child,.ant-btn[disabled]:focus>a:only-child,.ant-btn[disabled]:active>a:only-child{color:currentcolor}.ant-btn[disabled]>a:only-child::after,.ant-btn[disabled]:hover>a:only-child::after,.ant-btn[disabled]:focus>a:only-child::after,.ant-btn[disabled]:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn:hover,.ant-btn:focus,.ant-btn:active{text-decoration:none;background:#fff}.ant-btn>span{display:inline-block}.ant-btn-primary{color:#fff;border-color:#1890ff;background:#1890ff;text-shadow:0 -1px 0 rgba(0,0,0,.12);box-shadow:0 2px 0 rgba(0,0,0,.045)}.ant-btn-primary>a:only-child{color:currentcolor}.ant-btn-primary>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-primary:hover,.ant-btn-primary:focus{color:#fff;border-color:#40a9ff;background:#40a9ff}.ant-btn-primary:hover>a:only-child,.ant-btn-primary:focus>a:only-child{color:currentcolor}.ant-btn-primary:hover>a:only-child::after,.ant-btn-primary:focus>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-primary:active{color:#fff;border-color:#096dd9;background:#096dd9}.ant-btn-primary:active>a:only-child{color:currentcolor}.ant-btn-primary:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-primary[disabled],.ant-btn-primary[disabled]:hover,.ant-btn-primary[disabled]:focus,.ant-btn-primary[disabled]:active{color:rgba(0,0,0,.25);border-color:#d9d9d9;background:#f5f5f5;text-shadow:none;box-shadow:none}.ant-btn-primary[disabled]>a:only-child,.ant-btn-primary[disabled]:hover>a:only-child,.ant-btn-primary[disabled]:focus>a:only-child,.ant-btn-primary[disabled]:active>a:only-child{color:currentcolor}.ant-btn-primary[disabled]>a:only-child::after,.ant-btn-primary[disabled]:hover>a:only-child::after,.ant-btn-primary[disabled]:focus>a:only-child::after,.ant-btn-primary[disabled]:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-group .ant-btn-primary:not(:first-child):not(:last-child){border-right-color:#40a9ff;border-left-color:#40a9ff}.ant-btn-group .ant-btn-primary:not(:first-child):not(:last-child):disabled{border-color:#d9d9d9}.ant-btn-group .ant-btn-primary:first-child:not(:last-child){border-right-color:#40a9ff}.ant-btn-group .ant-btn-primary:first-child:not(:last-child)[disabled]{border-right-color:#d9d9d9}.ant-btn-group .ant-btn-primary:last-child:not(:first-child),.ant-btn-group .ant-btn-primary+.ant-btn-primary{border-left-color:#40a9ff}.ant-btn-group .ant-btn-primary:last-child:not(:first-child)[disabled],.ant-btn-group .ant-btn-primary+.ant-btn-primary[disabled]{border-left-color:#d9d9d9}.ant-btn-ghost{color:rgba(0,0,0,.85);border-color:#d9d9d9;background:rgba(0,0,0,0)}.ant-btn-ghost>a:only-child{color:currentcolor}.ant-btn-ghost>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-ghost:hover,.ant-btn-ghost:focus{color:#40a9ff;border-color:#40a9ff;background:rgba(0,0,0,0)}.ant-btn-ghost:hover>a:only-child,.ant-btn-ghost:focus>a:only-child{color:currentcolor}.ant-btn-ghost:hover>a:only-child::after,.ant-btn-ghost:focus>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-ghost:active{color:#096dd9;border-color:#096dd9;background:rgba(0,0,0,0)}.ant-btn-ghost:active>a:only-child{color:currentcolor}.ant-btn-ghost:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-ghost[disabled],.ant-btn-ghost[disabled]:hover,.ant-btn-ghost[disabled]:focus,.ant-btn-ghost[disabled]:active{color:rgba(0,0,0,.25);border-color:#d9d9d9;background:#f5f5f5;text-shadow:none;box-shadow:none}.ant-btn-ghost[disabled]>a:only-child,.ant-btn-ghost[disabled]:hover>a:only-child,.ant-btn-ghost[disabled]:focus>a:only-child,.ant-btn-ghost[disabled]:active>a:only-child{color:currentcolor}.ant-btn-ghost[disabled]>a:only-child::after,.ant-btn-ghost[disabled]:hover>a:only-child::after,.ant-btn-ghost[disabled]:focus>a:only-child::after,.ant-btn-ghost[disabled]:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-dashed{color:rgba(0,0,0,.85);border-color:#d9d9d9;background:#fff;border-style:dashed}.ant-btn-dashed>a:only-child{color:currentcolor}.ant-btn-dashed>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-dashed:hover,.ant-btn-dashed:focus{color:#40a9ff;border-color:#40a9ff;background:#fff}.ant-btn-dashed:hover>a:only-child,.ant-btn-dashed:focus>a:only-child{color:currentcolor}.ant-btn-dashed:hover>a:only-child::after,.ant-btn-dashed:focus>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-dashed:active{color:#096dd9;border-color:#096dd9;background:#fff}.ant-btn-dashed:active>a:only-child{color:currentcolor}.ant-btn-dashed:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-dashed[disabled],.ant-btn-dashed[disabled]:hover,.ant-btn-dashed[disabled]:focus,.ant-btn-dashed[disabled]:active{color:rgba(0,0,0,.25);border-color:#d9d9d9;background:#f5f5f5;text-shadow:none;box-shadow:none}.ant-btn-dashed[disabled]>a:only-child,.ant-btn-dashed[disabled]:hover>a:only-child,.ant-btn-dashed[disabled]:focus>a:only-child,.ant-btn-dashed[disabled]:active>a:only-child{color:currentcolor}.ant-btn-dashed[disabled]>a:only-child::after,.ant-btn-dashed[disabled]:hover>a:only-child::after,.ant-btn-dashed[disabled]:focus>a:only-child::after,.ant-btn-dashed[disabled]:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-danger{color:#fff;border-color:#ff4d4f;background:#ff4d4f;text-shadow:0 -1px 0 rgba(0,0,0,.12);box-shadow:0 2px 0 rgba(0,0,0,.045)}.ant-btn-danger>a:only-child{color:currentcolor}.ant-btn-danger>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-danger:hover,.ant-btn-danger:focus{color:#fff;border-color:#ff7875;background:#ff7875}.ant-btn-danger:hover>a:only-child,.ant-btn-danger:focus>a:only-child{color:currentcolor}.ant-btn-danger:hover>a:only-child::after,.ant-btn-danger:focus>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-danger:active{color:#fff;border-color:#d9363e;background:#d9363e}.ant-btn-danger:active>a:only-child{color:currentcolor}.ant-btn-danger:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-danger[disabled],.ant-btn-danger[disabled]:hover,.ant-btn-danger[disabled]:focus,.ant-btn-danger[disabled]:active{color:rgba(0,0,0,.25);border-color:#d9d9d9;background:#f5f5f5;text-shadow:none;box-shadow:none}.ant-btn-danger[disabled]>a:only-child,.ant-btn-danger[disabled]:hover>a:only-child,.ant-btn-danger[disabled]:focus>a:only-child,.ant-btn-danger[disabled]:active>a:only-child{color:currentcolor}.ant-btn-danger[disabled]>a:only-child::after,.ant-btn-danger[disabled]:hover>a:only-child::after,.ant-btn-danger[disabled]:focus>a:only-child::after,.ant-btn-danger[disabled]:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-link{color:#1890ff;border-color:rgba(0,0,0,0);background:rgba(0,0,0,0);box-shadow:none}.ant-btn-link>a:only-child{color:currentcolor}.ant-btn-link>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-link:hover,.ant-btn-link:focus{color:#40a9ff;border-color:#40a9ff;background:rgba(0,0,0,0)}.ant-btn-link:hover>a:only-child,.ant-btn-link:focus>a:only-child{color:currentcolor}.ant-btn-link:hover>a:only-child::after,.ant-btn-link:focus>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-link:active{color:#096dd9;border-color:#096dd9;background:rgba(0,0,0,0)}.ant-btn-link:active>a:only-child{color:currentcolor}.ant-btn-link:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-link[disabled],.ant-btn-link[disabled]:hover,.ant-btn-link[disabled]:focus,.ant-btn-link[disabled]:active{color:rgba(0,0,0,.25);border-color:#d9d9d9;background:#f5f5f5;text-shadow:none;box-shadow:none}.ant-btn-link[disabled]>a:only-child,.ant-btn-link[disabled]:hover>a:only-child,.ant-btn-link[disabled]:focus>a:only-child,.ant-btn-link[disabled]:active>a:only-child{color:currentcolor}.ant-btn-link[disabled]>a:only-child::after,.ant-btn-link[disabled]:hover>a:only-child::after,.ant-btn-link[disabled]:focus>a:only-child::after,.ant-btn-link[disabled]:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-link:hover{background:rgba(0,0,0,0)}.ant-btn-link:hover,.ant-btn-link:focus,.ant-btn-link:active{border-color:rgba(0,0,0,0)}.ant-btn-link[disabled],.ant-btn-link[disabled]:hover,.ant-btn-link[disabled]:focus,.ant-btn-link[disabled]:active{color:rgba(0,0,0,.25);border-color:rgba(0,0,0,0);background:rgba(0,0,0,0);text-shadow:none;box-shadow:none}.ant-btn-link[disabled]>a:only-child,.ant-btn-link[disabled]:hover>a:only-child,.ant-btn-link[disabled]:focus>a:only-child,.ant-btn-link[disabled]:active>a:only-child{color:currentcolor}.ant-btn-link[disabled]>a:only-child::after,.ant-btn-link[disabled]:hover>a:only-child::after,.ant-btn-link[disabled]:focus>a:only-child::after,.ant-btn-link[disabled]:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-text{color:rgba(0,0,0,.85);border-color:rgba(0,0,0,0);background:rgba(0,0,0,0);box-shadow:none}.ant-btn-text>a:only-child{color:currentcolor}.ant-btn-text>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-text:hover,.ant-btn-text:focus{color:#40a9ff;border-color:#40a9ff;background:rgba(0,0,0,0)}.ant-btn-text:hover>a:only-child,.ant-btn-text:focus>a:only-child{color:currentcolor}.ant-btn-text:hover>a:only-child::after,.ant-btn-text:focus>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-text:active{color:#096dd9;border-color:#096dd9;background:rgba(0,0,0,0)}.ant-btn-text:active>a:only-child{color:currentcolor}.ant-btn-text:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-text[disabled],.ant-btn-text[disabled]:hover,.ant-btn-text[disabled]:focus,.ant-btn-text[disabled]:active{color:rgba(0,0,0,.25);border-color:#d9d9d9;background:#f5f5f5;text-shadow:none;box-shadow:none}.ant-btn-text[disabled]>a:only-child,.ant-btn-text[disabled]:hover>a:only-child,.ant-btn-text[disabled]:focus>a:only-child,.ant-btn-text[disabled]:active>a:only-child{color:currentcolor}.ant-btn-text[disabled]>a:only-child::after,.ant-btn-text[disabled]:hover>a:only-child::after,.ant-btn-text[disabled]:focus>a:only-child::after,.ant-btn-text[disabled]:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-text:hover,.ant-btn-text:focus{color:rgba(0,0,0,.85);background:rgba(0,0,0,.018);border-color:rgba(0,0,0,0)}.ant-btn-text:active{color:rgba(0,0,0,.85);background:rgba(0,0,0,.028);border-color:rgba(0,0,0,0)}.ant-btn-text[disabled],.ant-btn-text[disabled]:hover,.ant-btn-text[disabled]:focus,.ant-btn-text[disabled]:active{color:rgba(0,0,0,.25);border-color:rgba(0,0,0,0);background:rgba(0,0,0,0);text-shadow:none;box-shadow:none}.ant-btn-text[disabled]>a:only-child,.ant-btn-text[disabled]:hover>a:only-child,.ant-btn-text[disabled]:focus>a:only-child,.ant-btn-text[disabled]:active>a:only-child{color:currentcolor}.ant-btn-text[disabled]>a:only-child::after,.ant-btn-text[disabled]:hover>a:only-child::after,.ant-btn-text[disabled]:focus>a:only-child::after,.ant-btn-text[disabled]:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-dangerous{color:#ff4d4f;border-color:#ff4d4f;background:#fff}.ant-btn-dangerous>a:only-child{color:currentcolor}.ant-btn-dangerous>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-dangerous:hover,.ant-btn-dangerous:focus{color:#ff7875;border-color:#ff7875;background:#fff}.ant-btn-dangerous:hover>a:only-child,.ant-btn-dangerous:focus>a:only-child{color:currentcolor}.ant-btn-dangerous:hover>a:only-child::after,.ant-btn-dangerous:focus>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-dangerous:active{color:#d9363e;border-color:#d9363e;background:#fff}.ant-btn-dangerous:active>a:only-child{color:currentcolor}.ant-btn-dangerous:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-dangerous[disabled],.ant-btn-dangerous[disabled]:hover,.ant-btn-dangerous[disabled]:focus,.ant-btn-dangerous[disabled]:active{color:rgba(0,0,0,.25);border-color:#d9d9d9;background:#f5f5f5;text-shadow:none;box-shadow:none}.ant-btn-dangerous[disabled]>a:only-child,.ant-btn-dangerous[disabled]:hover>a:only-child,.ant-btn-dangerous[disabled]:focus>a:only-child,.ant-btn-dangerous[disabled]:active>a:only-child{color:currentcolor}.ant-btn-dangerous[disabled]>a:only-child::after,.ant-btn-dangerous[disabled]:hover>a:only-child::after,.ant-btn-dangerous[disabled]:focus>a:only-child::after,.ant-btn-dangerous[disabled]:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-dangerous.ant-btn-primary{color:#fff;border-color:#ff4d4f;background:#ff4d4f;text-shadow:0 -1px 0 rgba(0,0,0,.12);box-shadow:0 2px 0 rgba(0,0,0,.045)}.ant-btn-dangerous.ant-btn-primary>a:only-child{color:currentcolor}.ant-btn-dangerous.ant-btn-primary>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-dangerous.ant-btn-primary:hover,.ant-btn-dangerous.ant-btn-primary:focus{color:#fff;border-color:#ff7875;background:#ff7875}.ant-btn-dangerous.ant-btn-primary:hover>a:only-child,.ant-btn-dangerous.ant-btn-primary:focus>a:only-child{color:currentcolor}.ant-btn-dangerous.ant-btn-primary:hover>a:only-child::after,.ant-btn-dangerous.ant-btn-primary:focus>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-dangerous.ant-btn-primary:active{color:#fff;border-color:#d9363e;background:#d9363e}.ant-btn-dangerous.ant-btn-primary:active>a:only-child{color:currentcolor}.ant-btn-dangerous.ant-btn-primary:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-dangerous.ant-btn-primary[disabled],.ant-btn-dangerous.ant-btn-primary[disabled]:hover,.ant-btn-dangerous.ant-btn-primary[disabled]:focus,.ant-btn-dangerous.ant-btn-primary[disabled]:active{color:rgba(0,0,0,.25);border-color:#d9d9d9;background:#f5f5f5;text-shadow:none;box-shadow:none}.ant-btn-dangerous.ant-btn-primary[disabled]>a:only-child,.ant-btn-dangerous.ant-btn-primary[disabled]:hover>a:only-child,.ant-btn-dangerous.ant-btn-primary[disabled]:focus>a:only-child,.ant-btn-dangerous.ant-btn-primary[disabled]:active>a:only-child{color:currentcolor}.ant-btn-dangerous.ant-btn-primary[disabled]>a:only-child::after,.ant-btn-dangerous.ant-btn-primary[disabled]:hover>a:only-child::after,.ant-btn-dangerous.ant-btn-primary[disabled]:focus>a:only-child::after,.ant-btn-dangerous.ant-btn-primary[disabled]:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-dangerous.ant-btn-link{color:#ff4d4f;border-color:rgba(0,0,0,0);background:rgba(0,0,0,0);box-shadow:none}.ant-btn-dangerous.ant-btn-link>a:only-child{color:currentcolor}.ant-btn-dangerous.ant-btn-link>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-dangerous.ant-btn-link:hover,.ant-btn-dangerous.ant-btn-link:focus{color:#40a9ff;border-color:#40a9ff;background:rgba(0,0,0,0)}.ant-btn-dangerous.ant-btn-link:hover>a:only-child,.ant-btn-dangerous.ant-btn-link:focus>a:only-child{color:currentcolor}.ant-btn-dangerous.ant-btn-link:hover>a:only-child::after,.ant-btn-dangerous.ant-btn-link:focus>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-dangerous.ant-btn-link:active{color:#096dd9;border-color:#096dd9;background:rgba(0,0,0,0)}.ant-btn-dangerous.ant-btn-link:active>a:only-child{color:currentcolor}.ant-btn-dangerous.ant-btn-link:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-dangerous.ant-btn-link[disabled],.ant-btn-dangerous.ant-btn-link[disabled]:hover,.ant-btn-dangerous.ant-btn-link[disabled]:focus,.ant-btn-dangerous.ant-btn-link[disabled]:active{color:rgba(0,0,0,.25);border-color:#d9d9d9;background:#f5f5f5;text-shadow:none;box-shadow:none}.ant-btn-dangerous.ant-btn-link[disabled]>a:only-child,.ant-btn-dangerous.ant-btn-link[disabled]:hover>a:only-child,.ant-btn-dangerous.ant-btn-link[disabled]:focus>a:only-child,.ant-btn-dangerous.ant-btn-link[disabled]:active>a:only-child{color:currentcolor}.ant-btn-dangerous.ant-btn-link[disabled]>a:only-child::after,.ant-btn-dangerous.ant-btn-link[disabled]:hover>a:only-child::after,.ant-btn-dangerous.ant-btn-link[disabled]:focus>a:only-child::after,.ant-btn-dangerous.ant-btn-link[disabled]:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-dangerous.ant-btn-link:hover,.ant-btn-dangerous.ant-btn-link:focus{color:#ff7875;border-color:rgba(0,0,0,0);background:rgba(0,0,0,0)}.ant-btn-dangerous.ant-btn-link:hover>a:only-child,.ant-btn-dangerous.ant-btn-link:focus>a:only-child{color:currentcolor}.ant-btn-dangerous.ant-btn-link:hover>a:only-child::after,.ant-btn-dangerous.ant-btn-link:focus>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-dangerous.ant-btn-link:active{color:#d9363e;border-color:rgba(0,0,0,0);background:rgba(0,0,0,0)}.ant-btn-dangerous.ant-btn-link:active>a:only-child{color:currentcolor}.ant-btn-dangerous.ant-btn-link:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-dangerous.ant-btn-link[disabled],.ant-btn-dangerous.ant-btn-link[disabled]:hover,.ant-btn-dangerous.ant-btn-link[disabled]:focus,.ant-btn-dangerous.ant-btn-link[disabled]:active{color:rgba(0,0,0,.25);border-color:rgba(0,0,0,0);background:rgba(0,0,0,0);text-shadow:none;box-shadow:none}.ant-btn-dangerous.ant-btn-link[disabled]>a:only-child,.ant-btn-dangerous.ant-btn-link[disabled]:hover>a:only-child,.ant-btn-dangerous.ant-btn-link[disabled]:focus>a:only-child,.ant-btn-dangerous.ant-btn-link[disabled]:active>a:only-child{color:currentcolor}.ant-btn-dangerous.ant-btn-link[disabled]>a:only-child::after,.ant-btn-dangerous.ant-btn-link[disabled]:hover>a:only-child::after,.ant-btn-dangerous.ant-btn-link[disabled]:focus>a:only-child::after,.ant-btn-dangerous.ant-btn-link[disabled]:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-dangerous.ant-btn-text{color:#ff4d4f;border-color:rgba(0,0,0,0);background:rgba(0,0,0,0);box-shadow:none}.ant-btn-dangerous.ant-btn-text>a:only-child{color:currentcolor}.ant-btn-dangerous.ant-btn-text>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-dangerous.ant-btn-text:hover,.ant-btn-dangerous.ant-btn-text:focus{color:#40a9ff;border-color:#40a9ff;background:rgba(0,0,0,0)}.ant-btn-dangerous.ant-btn-text:hover>a:only-child,.ant-btn-dangerous.ant-btn-text:focus>a:only-child{color:currentcolor}.ant-btn-dangerous.ant-btn-text:hover>a:only-child::after,.ant-btn-dangerous.ant-btn-text:focus>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-dangerous.ant-btn-text:active{color:#096dd9;border-color:#096dd9;background:rgba(0,0,0,0)}.ant-btn-dangerous.ant-btn-text:active>a:only-child{color:currentcolor}.ant-btn-dangerous.ant-btn-text:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-dangerous.ant-btn-text[disabled],.ant-btn-dangerous.ant-btn-text[disabled]:hover,.ant-btn-dangerous.ant-btn-text[disabled]:focus,.ant-btn-dangerous.ant-btn-text[disabled]:active{color:rgba(0,0,0,.25);border-color:#d9d9d9;background:#f5f5f5;text-shadow:none;box-shadow:none}.ant-btn-dangerous.ant-btn-text[disabled]>a:only-child,.ant-btn-dangerous.ant-btn-text[disabled]:hover>a:only-child,.ant-btn-dangerous.ant-btn-text[disabled]:focus>a:only-child,.ant-btn-dangerous.ant-btn-text[disabled]:active>a:only-child{color:currentcolor}.ant-btn-dangerous.ant-btn-text[disabled]>a:only-child::after,.ant-btn-dangerous.ant-btn-text[disabled]:hover>a:only-child::after,.ant-btn-dangerous.ant-btn-text[disabled]:focus>a:only-child::after,.ant-btn-dangerous.ant-btn-text[disabled]:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-dangerous.ant-btn-text:hover,.ant-btn-dangerous.ant-btn-text:focus{color:#ff7875;border-color:rgba(0,0,0,0);background:rgba(0,0,0,.018)}.ant-btn-dangerous.ant-btn-text:hover>a:only-child,.ant-btn-dangerous.ant-btn-text:focus>a:only-child{color:currentcolor}.ant-btn-dangerous.ant-btn-text:hover>a:only-child::after,.ant-btn-dangerous.ant-btn-text:focus>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-dangerous.ant-btn-text:active{color:#d9363e;border-color:rgba(0,0,0,0);background:rgba(0,0,0,.028)}.ant-btn-dangerous.ant-btn-text:active>a:only-child{color:currentcolor}.ant-btn-dangerous.ant-btn-text:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-dangerous.ant-btn-text[disabled],.ant-btn-dangerous.ant-btn-text[disabled]:hover,.ant-btn-dangerous.ant-btn-text[disabled]:focus,.ant-btn-dangerous.ant-btn-text[disabled]:active{color:rgba(0,0,0,.25);border-color:rgba(0,0,0,0);background:rgba(0,0,0,0);text-shadow:none;box-shadow:none}.ant-btn-dangerous.ant-btn-text[disabled]>a:only-child,.ant-btn-dangerous.ant-btn-text[disabled]:hover>a:only-child,.ant-btn-dangerous.ant-btn-text[disabled]:focus>a:only-child,.ant-btn-dangerous.ant-btn-text[disabled]:active>a:only-child{color:currentcolor}.ant-btn-dangerous.ant-btn-text[disabled]>a:only-child::after,.ant-btn-dangerous.ant-btn-text[disabled]:hover>a:only-child::after,.ant-btn-dangerous.ant-btn-text[disabled]:focus>a:only-child::after,.ant-btn-dangerous.ant-btn-text[disabled]:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-icon-only{width:32px;height:32px;padding:2.4px 0;font-size:16px;border-radius:2px;vertical-align:-3px}.ant-btn-icon-only>*{font-size:16px}.ant-btn-icon-only.ant-btn-lg{width:40px;height:40px;padding:4.9px 0;font-size:18px;border-radius:2px}.ant-btn-icon-only.ant-btn-lg>*{font-size:18px}.ant-btn-icon-only.ant-btn-sm{width:24px;height:24px;padding:0px 0;font-size:14px;border-radius:2px}.ant-btn-icon-only.ant-btn-sm>*{font-size:14px}.ant-btn-icon-only>.anticon{display:flex;justify-content:center}.ant-btn-icon-only .anticon-loading{padding:0 !important}a.ant-btn-icon-only{vertical-align:-1px}a.ant-btn-icon-only>.anticon{display:inline}.ant-btn-round{height:32px;padding:4px 16px;font-size:14px;border-radius:32px}.ant-btn-round.ant-btn-lg{height:40px;padding:6.4px 20px;font-size:16px;border-radius:40px}.ant-btn-round.ant-btn-sm{height:24px;padding:0px 12px;font-size:14px;border-radius:24px}.ant-btn-round.ant-btn-icon-only{width:auto}.ant-btn-circle{min-width:32px;padding-right:0;padding-left:0;text-align:center;border-radius:50%}.ant-btn-circle.ant-btn-lg{min-width:40px;border-radius:50%}.ant-btn-circle.ant-btn-sm{min-width:24px;border-radius:50%}.ant-btn::before{position:absolute;top:-1px;right:-1px;bottom:-1px;left:-1px;z-index:1;display:none;background:#fff;border-radius:inherit;opacity:.35;transition:opacity .2s;content:"";pointer-events:none}.ant-btn .anticon{transition:margin-left .3s cubic-bezier(0.645, 0.045, 0.355, 1)}.ant-btn .anticon.anticon-plus>svg,.ant-btn .anticon.anticon-minus>svg{shape-rendering:optimizespeed}.ant-btn.ant-btn-loading{position:relative;cursor:default}.ant-btn.ant-btn-loading::before{display:block}.ant-btn>.ant-btn-loading-icon{transition:width .3s cubic-bezier(0.645, 0.045, 0.355, 1),opacity .3s cubic-bezier(0.645, 0.045, 0.355, 1)}.ant-btn>.ant-btn-loading-icon .anticon{padding-right:8px;animation:none}.ant-btn>.ant-btn-loading-icon .anticon svg{animation:loadingCircle 1s infinite linear}.ant-btn-group{position:relative;display:inline-flex}.ant-btn-group>.ant-btn,.ant-btn-group>span>.ant-btn{position:relative}.ant-btn-group>.ant-btn:hover,.ant-btn-group>span>.ant-btn:hover,.ant-btn-group>.ant-btn:focus,.ant-btn-group>span>.ant-btn:focus,.ant-btn-group>.ant-btn:active,.ant-btn-group>span>.ant-btn:active{z-index:2}.ant-btn-group>.ant-btn[disabled],.ant-btn-group>span>.ant-btn[disabled]{z-index:0}.ant-btn-group .ant-btn-icon-only{font-size:14px}.ant-btn-group .ant-btn+.ant-btn,.ant-btn+.ant-btn-group,.ant-btn-group span+.ant-btn,.ant-btn-group .ant-btn+span,.ant-btn-group>span+span,.ant-btn-group+.ant-btn,.ant-btn-group+.ant-btn-group{margin-left:-1px}.ant-btn-group .ant-btn-primary+.ant-btn:not(.ant-btn-primary):not([disabled]){border-left-color:rgba(0,0,0,0)}.ant-btn-group .ant-btn{border-radius:0}.ant-btn-group>.ant-btn:first-child,.ant-btn-group>span:first-child>.ant-btn{margin-left:0}.ant-btn-group>.ant-btn:only-child{border-radius:2px}.ant-btn-group>span:only-child>.ant-btn{border-radius:2px}.ant-btn-group>.ant-btn:first-child:not(:last-child),.ant-btn-group>span:first-child:not(:last-child)>.ant-btn{border-top-left-radius:2px;border-bottom-left-radius:2px}.ant-btn-group>.ant-btn:last-child:not(:first-child),.ant-btn-group>span:last-child:not(:first-child)>.ant-btn{border-top-right-radius:2px;border-bottom-right-radius:2px}.ant-btn-group-sm>.ant-btn:only-child{border-radius:2px}.ant-btn-group-sm>span:only-child>.ant-btn{border-radius:2px}.ant-btn-group-sm>.ant-btn:first-child:not(:last-child),.ant-btn-group-sm>span:first-child:not(:last-child)>.ant-btn{border-top-left-radius:2px;border-bottom-left-radius:2px}.ant-btn-group-sm>.ant-btn:last-child:not(:first-child),.ant-btn-group-sm>span:last-child:not(:first-child)>.ant-btn{border-top-right-radius:2px;border-bottom-right-radius:2px}.ant-btn-group>.ant-btn-group{float:left}.ant-btn-group>.ant-btn-group:not(:first-child):not(:last-child)>.ant-btn{border-radius:0}.ant-btn-group>.ant-btn-group:first-child:not(:last-child)>.ant-btn:last-child{padding-right:8px;border-top-right-radius:0;border-bottom-right-radius:0}.ant-btn-group>.ant-btn-group:last-child:not(:first-child)>.ant-btn:first-child{padding-left:8px;border-top-left-radius:0;border-bottom-left-radius:0}.ant-btn-rtl.ant-btn-group .ant-btn+.ant-btn,.ant-btn-rtl.ant-btn+.ant-btn-group,.ant-btn-rtl.ant-btn-group span+.ant-btn,.ant-btn-rtl.ant-btn-group .ant-btn+span,.ant-btn-rtl.ant-btn-group>span+span,.ant-btn-rtl.ant-btn-group+.ant-btn,.ant-btn-rtl.ant-btn-group+.ant-btn-group,.ant-btn-group-rtl.ant-btn-group .ant-btn+.ant-btn,.ant-btn-group-rtl.ant-btn+.ant-btn-group,.ant-btn-group-rtl.ant-btn-group span+.ant-btn,.ant-btn-group-rtl.ant-btn-group .ant-btn+span,.ant-btn-group-rtl.ant-btn-group>span+span,.ant-btn-group-rtl.ant-btn-group+.ant-btn,.ant-btn-group-rtl.ant-btn-group+.ant-btn-group{margin-right:-1px;margin-left:auto}.ant-btn-group.ant-btn-group-rtl{direction:rtl}.ant-btn-group-rtl.ant-btn-group>.ant-btn:first-child:not(:last-child),.ant-btn-group-rtl.ant-btn-group>span:first-child:not(:last-child)>.ant-btn{border-radius:0 2px 2px 0}.ant-btn-group-rtl.ant-btn-group>.ant-btn:last-child:not(:first-child),.ant-btn-group-rtl.ant-btn-group>span:last-child:not(:first-child)>.ant-btn{border-radius:2px 0 0 2px}.ant-btn-group-rtl.ant-btn-group-sm>.ant-btn:first-child:not(:last-child),.ant-btn-group-rtl.ant-btn-group-sm>span:first-child:not(:last-child)>.ant-btn{border-radius:0 2px 2px 0}.ant-btn-group-rtl.ant-btn-group-sm>.ant-btn:last-child:not(:first-child),.ant-btn-group-rtl.ant-btn-group-sm>span:last-child:not(:first-child)>.ant-btn{border-radius:2px 0 0 2px}.ant-btn:focus>span,.ant-btn:active>span{position:relative}.ant-btn>.anticon+span,.ant-btn>span+.anticon{margin-left:8px}.ant-btn.ant-btn-background-ghost{color:#fff;border-color:#fff}.ant-btn.ant-btn-background-ghost,.ant-btn.ant-btn-background-ghost:hover,.ant-btn.ant-btn-background-ghost:active,.ant-btn.ant-btn-background-ghost:focus{background:rgba(0,0,0,0)}.ant-btn.ant-btn-background-ghost:hover,.ant-btn.ant-btn-background-ghost:focus{color:#40a9ff;border-color:#40a9ff}.ant-btn.ant-btn-background-ghost:active{color:#096dd9;border-color:#096dd9}.ant-btn.ant-btn-background-ghost[disabled]{color:rgba(0,0,0,.25);background:rgba(0,0,0,0);border-color:#d9d9d9}.ant-btn-background-ghost.ant-btn-primary{color:#1890ff;border-color:#1890ff;text-shadow:none}.ant-btn-background-ghost.ant-btn-primary>a:only-child{color:currentcolor}.ant-btn-background-ghost.ant-btn-primary>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-background-ghost.ant-btn-primary:hover,.ant-btn-background-ghost.ant-btn-primary:focus{color:#40a9ff;border-color:#40a9ff}.ant-btn-background-ghost.ant-btn-primary:hover>a:only-child,.ant-btn-background-ghost.ant-btn-primary:focus>a:only-child{color:currentcolor}.ant-btn-background-ghost.ant-btn-primary:hover>a:only-child::after,.ant-btn-background-ghost.ant-btn-primary:focus>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-background-ghost.ant-btn-primary:active{color:#096dd9;border-color:#096dd9}.ant-btn-background-ghost.ant-btn-primary:active>a:only-child{color:currentcolor}.ant-btn-background-ghost.ant-btn-primary:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-background-ghost.ant-btn-primary[disabled],.ant-btn-background-ghost.ant-btn-primary[disabled]:hover,.ant-btn-background-ghost.ant-btn-primary[disabled]:focus,.ant-btn-background-ghost.ant-btn-primary[disabled]:active{color:rgba(0,0,0,.25);border-color:#d9d9d9;background:#f5f5f5;text-shadow:none;box-shadow:none}.ant-btn-background-ghost.ant-btn-primary[disabled]>a:only-child,.ant-btn-background-ghost.ant-btn-primary[disabled]:hover>a:only-child,.ant-btn-background-ghost.ant-btn-primary[disabled]:focus>a:only-child,.ant-btn-background-ghost.ant-btn-primary[disabled]:active>a:only-child{color:currentcolor}.ant-btn-background-ghost.ant-btn-primary[disabled]>a:only-child::after,.ant-btn-background-ghost.ant-btn-primary[disabled]:hover>a:only-child::after,.ant-btn-background-ghost.ant-btn-primary[disabled]:focus>a:only-child::after,.ant-btn-background-ghost.ant-btn-primary[disabled]:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-background-ghost.ant-btn-danger{color:#ff4d4f;border-color:#ff4d4f;text-shadow:none}.ant-btn-background-ghost.ant-btn-danger>a:only-child{color:currentcolor}.ant-btn-background-ghost.ant-btn-danger>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-background-ghost.ant-btn-danger:hover,.ant-btn-background-ghost.ant-btn-danger:focus{color:#ff7875;border-color:#ff7875}.ant-btn-background-ghost.ant-btn-danger:hover>a:only-child,.ant-btn-background-ghost.ant-btn-danger:focus>a:only-child{color:currentcolor}.ant-btn-background-ghost.ant-btn-danger:hover>a:only-child::after,.ant-btn-background-ghost.ant-btn-danger:focus>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-background-ghost.ant-btn-danger:active{color:#d9363e;border-color:#d9363e}.ant-btn-background-ghost.ant-btn-danger:active>a:only-child{color:currentcolor}.ant-btn-background-ghost.ant-btn-danger:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-background-ghost.ant-btn-danger[disabled],.ant-btn-background-ghost.ant-btn-danger[disabled]:hover,.ant-btn-background-ghost.ant-btn-danger[disabled]:focus,.ant-btn-background-ghost.ant-btn-danger[disabled]:active{color:rgba(0,0,0,.25);border-color:#d9d9d9;background:#f5f5f5;text-shadow:none;box-shadow:none}.ant-btn-background-ghost.ant-btn-danger[disabled]>a:only-child,.ant-btn-background-ghost.ant-btn-danger[disabled]:hover>a:only-child,.ant-btn-background-ghost.ant-btn-danger[disabled]:focus>a:only-child,.ant-btn-background-ghost.ant-btn-danger[disabled]:active>a:only-child{color:currentcolor}.ant-btn-background-ghost.ant-btn-danger[disabled]>a:only-child::after,.ant-btn-background-ghost.ant-btn-danger[disabled]:hover>a:only-child::after,.ant-btn-background-ghost.ant-btn-danger[disabled]:focus>a:only-child::after,.ant-btn-background-ghost.ant-btn-danger[disabled]:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-background-ghost.ant-btn-dangerous{color:#ff4d4f;border-color:#ff4d4f;text-shadow:none}.ant-btn-background-ghost.ant-btn-dangerous>a:only-child{color:currentcolor}.ant-btn-background-ghost.ant-btn-dangerous>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-background-ghost.ant-btn-dangerous:hover,.ant-btn-background-ghost.ant-btn-dangerous:focus{color:#ff7875;border-color:#ff7875}.ant-btn-background-ghost.ant-btn-dangerous:hover>a:only-child,.ant-btn-background-ghost.ant-btn-dangerous:focus>a:only-child{color:currentcolor}.ant-btn-background-ghost.ant-btn-dangerous:hover>a:only-child::after,.ant-btn-background-ghost.ant-btn-dangerous:focus>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-background-ghost.ant-btn-dangerous:active{color:#d9363e;border-color:#d9363e}.ant-btn-background-ghost.ant-btn-dangerous:active>a:only-child{color:currentcolor}.ant-btn-background-ghost.ant-btn-dangerous:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-background-ghost.ant-btn-dangerous[disabled],.ant-btn-background-ghost.ant-btn-dangerous[disabled]:hover,.ant-btn-background-ghost.ant-btn-dangerous[disabled]:focus,.ant-btn-background-ghost.ant-btn-dangerous[disabled]:active{color:rgba(0,0,0,.25);border-color:#d9d9d9;background:#f5f5f5;text-shadow:none;box-shadow:none}.ant-btn-background-ghost.ant-btn-dangerous[disabled]>a:only-child,.ant-btn-background-ghost.ant-btn-dangerous[disabled]:hover>a:only-child,.ant-btn-background-ghost.ant-btn-dangerous[disabled]:focus>a:only-child,.ant-btn-background-ghost.ant-btn-dangerous[disabled]:active>a:only-child{color:currentcolor}.ant-btn-background-ghost.ant-btn-dangerous[disabled]>a:only-child::after,.ant-btn-background-ghost.ant-btn-dangerous[disabled]:hover>a:only-child::after,.ant-btn-background-ghost.ant-btn-dangerous[disabled]:focus>a:only-child::after,.ant-btn-background-ghost.ant-btn-dangerous[disabled]:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-background-ghost.ant-btn-dangerous.ant-btn-link{color:#ff4d4f;border-color:rgba(0,0,0,0);text-shadow:none}.ant-btn-background-ghost.ant-btn-dangerous.ant-btn-link>a:only-child{color:currentcolor}.ant-btn-background-ghost.ant-btn-dangerous.ant-btn-link>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-background-ghost.ant-btn-dangerous.ant-btn-link:hover,.ant-btn-background-ghost.ant-btn-dangerous.ant-btn-link:focus{color:#ff7875;border-color:rgba(0,0,0,0)}.ant-btn-background-ghost.ant-btn-dangerous.ant-btn-link:hover>a:only-child,.ant-btn-background-ghost.ant-btn-dangerous.ant-btn-link:focus>a:only-child{color:currentcolor}.ant-btn-background-ghost.ant-btn-dangerous.ant-btn-link:hover>a:only-child::after,.ant-btn-background-ghost.ant-btn-dangerous.ant-btn-link:focus>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-background-ghost.ant-btn-dangerous.ant-btn-link:active{color:#d9363e;border-color:rgba(0,0,0,0)}.ant-btn-background-ghost.ant-btn-dangerous.ant-btn-link:active>a:only-child{color:currentcolor}.ant-btn-background-ghost.ant-btn-dangerous.ant-btn-link:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-background-ghost.ant-btn-dangerous.ant-btn-link[disabled],.ant-btn-background-ghost.ant-btn-dangerous.ant-btn-link[disabled]:hover,.ant-btn-background-ghost.ant-btn-dangerous.ant-btn-link[disabled]:focus,.ant-btn-background-ghost.ant-btn-dangerous.ant-btn-link[disabled]:active{color:rgba(0,0,0,.25);border-color:#d9d9d9;background:#f5f5f5;text-shadow:none;box-shadow:none}.ant-btn-background-ghost.ant-btn-dangerous.ant-btn-link[disabled]>a:only-child,.ant-btn-background-ghost.ant-btn-dangerous.ant-btn-link[disabled]:hover>a:only-child,.ant-btn-background-ghost.ant-btn-dangerous.ant-btn-link[disabled]:focus>a:only-child,.ant-btn-background-ghost.ant-btn-dangerous.ant-btn-link[disabled]:active>a:only-child{color:currentcolor}.ant-btn-background-ghost.ant-btn-dangerous.ant-btn-link[disabled]>a:only-child::after,.ant-btn-background-ghost.ant-btn-dangerous.ant-btn-link[disabled]:hover>a:only-child::after,.ant-btn-background-ghost.ant-btn-dangerous.ant-btn-link[disabled]:focus>a:only-child::after,.ant-btn-background-ghost.ant-btn-dangerous.ant-btn-link[disabled]:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}.ant-btn-two-chinese-chars::first-letter{letter-spacing:.34em}.ant-btn-two-chinese-chars>*:not(.anticon){margin-right:-0.34em;letter-spacing:.34em}.ant-btn.ant-btn-block{width:100%}.ant-btn:empty{display:inline-block;width:0;visibility:hidden;content:"&nbsp;"}a.ant-btn{padding-top:.01px !important;line-height:30px}a.ant-btn-disabled{cursor:not-allowed}a.ant-btn-disabled>*{pointer-events:none}a.ant-btn-disabled,a.ant-btn-disabled:hover,a.ant-btn-disabled:focus,a.ant-btn-disabled:active{color:rgba(0,0,0,.25);border-color:rgba(0,0,0,0);background:rgba(0,0,0,0);text-shadow:none;box-shadow:none}a.ant-btn-disabled>a:only-child,a.ant-btn-disabled:hover>a:only-child,a.ant-btn-disabled:focus>a:only-child,a.ant-btn-disabled:active>a:only-child{color:currentcolor}a.ant-btn-disabled>a:only-child::after,a.ant-btn-disabled:hover>a:only-child::after,a.ant-btn-disabled:focus>a:only-child::after,a.ant-btn-disabled:active>a:only-child::after{position:absolute;top:0;right:0;bottom:0;left:0;background:rgba(0,0,0,0);content:""}a.ant-btn-lg{line-height:38px}a.ant-btn-sm{line-height:22px}.ant-btn-compact-item:not(.ant-btn-compact-last-item):not(.ant-btn-compact-item-rtl){margin-right:-1px}.ant-btn-compact-item:not(.ant-btn-compact-last-item).ant-btn-compact-item-rtl{margin-left:-1px}.ant-btn-compact-item:hover,.ant-btn-compact-item:focus,.ant-btn-compact-item:active{z-index:2}.ant-btn-compact-item[disabled]{z-index:0}.ant-btn-compact-item:not(.ant-btn-compact-first-item):not(.ant-btn-compact-last-item).ant-btn{border-radius:0}.ant-btn-compact-item.ant-btn.ant-btn-compact-first-item:not(.ant-btn-compact-last-item):not(.ant-btn-compact-item-rtl){border-top-right-radius:0;border-bottom-right-radius:0}.ant-btn-compact-item.ant-btn.ant-btn-compact-last-item:not(.ant-btn-compact-first-item):not(.ant-btn-compact-item-rtl){border-top-left-radius:0;border-bottom-left-radius:0}.ant-btn-compact-item.ant-btn.ant-btn-compact-item-rtl.ant-btn-compact-first-item:not(.ant-btn-compact-last-item){border-top-left-radius:0;border-bottom-left-radius:0}.ant-btn-compact-item.ant-btn.ant-btn-compact-item-rtl.ant-btn-compact-last-item:not(.ant-btn-compact-first-item){border-top-right-radius:0;border-bottom-right-radius:0}.ant-btn-icon-only.ant-btn-compact-item{flex:none}.ant-btn-compact-item.ant-btn-primary:not([disabled])+.ant-btn-compact-item.ant-btn-primary:not([disabled]){position:relative}.ant-btn-compact-item.ant-btn-primary:not([disabled])+.ant-btn-compact-item.ant-btn-primary:not([disabled])::after{position:absolute;top:-1px;left:-1px;display:inline-block;width:1px;height:calc(100% + 2px);background-color:#40a9ff;content:" "}.ant-btn-compact-item-rtl.ant-btn-compact-first-item.ant-btn-compact-item-rtl:not(.ant-btn-compact-last-item){border-top-left-radius:0;border-bottom-left-radius:0}.ant-btn-compact-item-rtl.ant-btn-compact-last-item.ant-btn-compact-item-rtl:not(.ant-btn-compact-first-item){border-top-right-radius:0;border-bottom-right-radius:0}.ant-btn-compact-item-rtl.ant-btn-sm.ant-btn-compact-first-item.ant-btn-compact-item-rtl.ant-btn-sm:not(.ant-btn-compact-last-item){border-top-left-radius:0;border-bottom-left-radius:0}.ant-btn-compact-item-rtl.ant-btn-sm.ant-btn-compact-last-item.ant-btn-compact-item-rtl.ant-btn-sm:not(.ant-btn-compact-first-item){border-top-right-radius:0;border-bottom-right-radius:0}.ant-btn-compact-item-rtl.ant-btn-primary:not([disabled])+.ant-btn-compact-item-rtl.ant-btn-primary:not([disabled])::after{right:-1px}.ant-btn-compact-vertical-item:not(.ant-btn-compact-vertical-last-item){margin-bottom:-1px}.ant-btn-compact-vertical-item:hover,.ant-btn-compact-vertical-item:focus,.ant-btn-compact-vertical-item:active{z-index:2}.ant-btn-compact-vertical-item[disabled]{z-index:0}.ant-btn-compact-vertical-item:not(.ant-btn-compact-vertical-first-item):not(.ant-btn-compact-vertical-last-item){border-radius:0}.ant-btn-compact-vertical-item.ant-btn-compact-vertical-first-item:not(.ant-btn-compact-vertical-last-item){border-bottom-right-radius:0;border-bottom-left-radius:0}.ant-btn-compact-vertical-item.ant-btn-compact-vertical-last-item:not(.ant-btn-compact-vertical-first-item){border-top-left-radius:0;border-top-right-radius:0}.ant-btn-compact-vertical-item.ant-btn-primary:not([disabled])+.ant-btn-compact-vertical-item.ant-btn-primary:not([disabled]){position:relative}.ant-btn-compact-vertical-item.ant-btn-primary:not([disabled])+.ant-btn-compact-vertical-item.ant-btn-primary:not([disabled])::after{position:absolute;top:-1px;left:-1px;display:inline-block;width:calc(100% + 2px);height:1px;background-color:#40a9ff;content:" "}.ant-btn-rtl{direction:rtl}.ant-btn-group-rtl.ant-btn-group .ant-btn-primary:last-child:not(:first-child),.ant-btn-group-rtl.ant-btn-group .ant-btn-primary+.ant-btn-primary{border-right-color:#40a9ff;border-left-color:#d9d9d9}.ant-btn-group-rtl.ant-btn-group .ant-btn-primary:last-child:not(:first-child)[disabled],.ant-btn-group-rtl.ant-btn-group .ant-btn-primary+.ant-btn-primary[disabled]{border-right-color:#d9d9d9;border-left-color:#40a9ff}.ant-btn-rtl.ant-btn>.ant-btn-loading-icon .anticon{padding-right:0;padding-left:8px}.ant-btn-rtl.ant-btn>.anticon+span,.ant-btn-rtl.ant-btn>span+.anticon{margin-right:8px;margin-left:0}</style><style>.ant-carousel{box-sizing:border-box;margin:0;padding:0;color:rgba(0,0,0,.85);font-size:14px;font-variant:tabular-nums;line-height:1.5715;list-style:none;font-feature-settings:"tnum"}.ant-carousel .slick-slider{position:relative;display:block;box-sizing:border-box;touch-action:pan-y;-webkit-touch-callout:none;-webkit-tap-highlight-color:rgba(0,0,0,0)}.ant-carousel .slick-list{position:relative;display:block;margin:0;padding:0;overflow:hidden}.ant-carousel .slick-list:focus{outline:none}.ant-carousel .slick-list.dragging{cursor:pointer}.ant-carousel .slick-list .slick-slide{pointer-events:none}.ant-carousel .slick-list .slick-slide input.ant-radio-input,.ant-carousel .slick-list .slick-slide input.ant-checkbox-input{visibility:hidden}.ant-carousel .slick-list .slick-slide.slick-active{pointer-events:auto}.ant-carousel .slick-list .slick-slide.slick-active input.ant-radio-input,.ant-carousel .slick-list .slick-slide.slick-active input.ant-checkbox-input{visibility:visible}.ant-carousel .slick-list .slick-slide>div>div{vertical-align:bottom}.ant-carousel .slick-slider .slick-track,.ant-carousel .slick-slider .slick-list{transform:translate3d(0, 0, 0);touch-action:pan-y}.ant-carousel .slick-track{position:relative;top:0;left:0;display:block}.ant-carousel .slick-track::before,.ant-carousel .slick-track::after{display:table;content:""}.ant-carousel .slick-track::after{clear:both}.slick-loading .ant-carousel .slick-track{visibility:hidden}.ant-carousel .slick-slide{display:none;float:left;height:100%;min-height:1px}.ant-carousel .slick-slide img{display:block}.ant-carousel .slick-slide.slick-loading img{display:none}.ant-carousel .slick-slide.dragging img{pointer-events:none}.ant-carousel .slick-initialized .slick-slide{display:block}.ant-carousel .slick-loading .slick-slide{visibility:hidden}.ant-carousel .slick-vertical .slick-slide{display:block;height:auto}.ant-carousel .slick-arrow.slick-hidden{display:none}.ant-carousel .slick-prev,.ant-carousel .slick-next{position:absolute;top:50%;display:block;width:20px;height:20px;margin-top:-10px;padding:0;color:rgba(0,0,0,0);font-size:0;line-height:0;background:rgba(0,0,0,0);border:0;outline:none;cursor:pointer}.ant-carousel .slick-prev:hover,.ant-carousel .slick-next:hover,.ant-carousel .slick-prev:focus,.ant-carousel .slick-next:focus{color:rgba(0,0,0,0);background:rgba(0,0,0,0);outline:none}.ant-carousel .slick-prev:hover::before,.ant-carousel .slick-next:hover::before,.ant-carousel .slick-prev:focus::before,.ant-carousel .slick-next:focus::before{opacity:1}.ant-carousel .slick-prev.slick-disabled::before,.ant-carousel .slick-next.slick-disabled::before{opacity:.25}.ant-carousel .slick-prev{left:-25px}.ant-carousel .slick-prev::before{content:"←"}.ant-carousel .slick-next{right:-25px}.ant-carousel .slick-next::before{content:"→"}.ant-carousel .slick-dots{position:absolute;right:0;bottom:0;left:0;z-index:15;display:flex !important;justify-content:center;margin-right:15%;margin-bottom:0;margin-left:15%;padding-left:0;list-style:none}.ant-carousel .slick-dots-bottom{bottom:12px}.ant-carousel .slick-dots-top{top:12px;bottom:auto}.ant-carousel .slick-dots li{position:relative;display:inline-block;flex:0 1 auto;box-sizing:content-box;width:16px;height:3px;margin:0 4px;padding:0;text-align:center;text-indent:-999px;vertical-align:top;transition:all .5s}.ant-carousel .slick-dots li button{position:relative;display:block;width:100%;height:3px;padding:0;color:rgba(0,0,0,0);font-size:0;background:#fff;border:0;border-radius:1px;outline:none;cursor:pointer;opacity:.3;transition:all .5s}.ant-carousel .slick-dots li button:hover,.ant-carousel .slick-dots li button:focus{opacity:.75}.ant-carousel .slick-dots li button::after{position:absolute;top:-4px;right:-4px;bottom:-4px;left:-4px;content:""}.ant-carousel .slick-dots li.slick-active{width:24px}.ant-carousel .slick-dots li.slick-active button{background:#fff;opacity:1}.ant-carousel .slick-dots li.slick-active:hover,.ant-carousel .slick-dots li.slick-active:focus{opacity:1}.ant-carousel-vertical .slick-dots{top:50%;bottom:auto;flex-direction:column;width:3px;height:auto;margin:0;transform:translateY(-50%)}.ant-carousel-vertical .slick-dots-left{right:auto;left:12px}.ant-carousel-vertical .slick-dots-right{right:12px;left:auto}.ant-carousel-vertical .slick-dots li{width:3px;height:16px;margin:4px 0;vertical-align:baseline}.ant-carousel-vertical .slick-dots li button{width:3px;height:16px}.ant-carousel-vertical .slick-dots li.slick-active{width:3px;height:24px}.ant-carousel-vertical .slick-dots li.slick-active button{width:3px;height:24px}.ant-carousel-rtl{direction:rtl}.ant-carousel-rtl .ant-carousel .slick-track{right:0;left:auto}.ant-carousel-rtl .ant-carousel .slick-prev{right:-25px;left:auto}.ant-carousel-rtl .ant-carousel .slick-prev::before{content:"→"}.ant-carousel-rtl .ant-carousel .slick-next{right:auto;left:-25px}.ant-carousel-rtl .ant-carousel .slick-next::before{content:"←"}.ant-carousel-rtl.ant-carousel .slick-dots{flex-direction:row-reverse}.ant-carousel-rtl.ant-carousel-vertical .slick-dots{flex-direction:column}</style><style>.ant-form-item .ant-input-number+.ant-form-text{margin-left:8px}.ant-form-inline{display:flex;flex-wrap:wrap}.ant-form-inline .ant-form-item{flex:none;flex-wrap:nowrap;margin-right:16px;margin-bottom:0}.ant-form-inline .ant-form-item-with-help{margin-bottom:24px}.ant-form-inline .ant-form-item>.ant-form-item-label,.ant-form-inline .ant-form-item>.ant-form-item-control{display:inline-block;vertical-align:top}.ant-form-inline .ant-form-item>.ant-form-item-label{flex:none}.ant-form-inline .ant-form-item .ant-form-text{display:inline-block}.ant-form-inline .ant-form-item .ant-form-item-has-feedback{display:inline-block}.ant-form-horizontal .ant-form-item-label{flex-grow:0}.ant-form-horizontal .ant-form-item-control{flex:1 1 0;min-width:0}.ant-form-horizontal .ant-form-item-label[class$="-24"]+.ant-form-item-control,.ant-form-horizontal .ant-form-item-label[class*="-24 "]+.ant-form-item-control{min-width:unset}.ant-form-vertical .ant-form-item-row{flex-direction:column}.ant-form-vertical .ant-form-item-label>label{height:auto}.ant-form-vertical .ant-form-item .ant-form-item-control{width:100%}.ant-form-vertical .ant-form-item-label,.ant-col-24.ant-form-item-label,.ant-col-xl-24.ant-form-item-label{padding:0 0 8px;line-height:1.5715;white-space:initial;text-align:left}.ant-form-vertical .ant-form-item-label>label,.ant-col-24.ant-form-item-label>label,.ant-col-xl-24.ant-form-item-label>label{margin:0}.ant-form-vertical .ant-form-item-label>label::after,.ant-col-24.ant-form-item-label>label::after,.ant-col-xl-24.ant-form-item-label>label::after{display:none}.ant-form-rtl.ant-form-vertical .ant-form-item-label,.ant-form-rtl.ant-col-24.ant-form-item-label,.ant-form-rtl.ant-col-xl-24.ant-form-item-label{text-align:right}@media(max-width: 575px){.ant-form-item .ant-form-item-label{padding:0 0 8px;line-height:1.5715;white-space:initial;text-align:left}.ant-form-item .ant-form-item-label>label{margin:0}.ant-form-item .ant-form-item-label>label::after{display:none}.ant-form-rtl.ant-form-item .ant-form-item-label{text-align:right}.ant-form .ant-form-item{flex-wrap:wrap}.ant-form .ant-form-item .ant-form-item-label,.ant-form .ant-form-item .ant-form-item-control{flex:0 0 100%;max-width:100%}.ant-col-xs-24.ant-form-item-label{padding:0 0 8px;line-height:1.5715;white-space:initial;text-align:left}.ant-col-xs-24.ant-form-item-label>label{margin:0}.ant-col-xs-24.ant-form-item-label>label::after{display:none}.ant-form-rtl.ant-col-xs-24.ant-form-item-label{text-align:right}}@media(max-width: 767px){.ant-col-sm-24.ant-form-item-label{padding:0 0 8px;line-height:1.5715;white-space:initial;text-align:left}.ant-col-sm-24.ant-form-item-label>label{margin:0}.ant-col-sm-24.ant-form-item-label>label::after{display:none}.ant-form-rtl.ant-col-sm-24.ant-form-item-label{text-align:right}}@media(max-width: 991px){.ant-col-md-24.ant-form-item-label{padding:0 0 8px;line-height:1.5715;white-space:initial;text-align:left}.ant-col-md-24.ant-form-item-label>label{margin:0}.ant-col-md-24.ant-form-item-label>label::after{display:none}.ant-form-rtl.ant-col-md-24.ant-form-item-label{text-align:right}}@media(max-width: 1199px){.ant-col-lg-24.ant-form-item-label{padding:0 0 8px;line-height:1.5715;white-space:initial;text-align:left}.ant-col-lg-24.ant-form-item-label>label{margin:0}.ant-col-lg-24.ant-form-item-label>label::after{display:none}.ant-form-rtl.ant-col-lg-24.ant-form-item-label{text-align:right}}@media(max-width: 1599px){.ant-col-xl-24.ant-form-item-label{padding:0 0 8px;line-height:1.5715;white-space:initial;text-align:left}.ant-col-xl-24.ant-form-item-label>label{margin:0}.ant-col-xl-24.ant-form-item-label>label::after{display:none}.ant-form-rtl.ant-col-xl-24.ant-form-item-label{text-align:right}}.ant-form-item-explain-error{color:#ff4d4f}.ant-form-item-explain-warning{color:#faad14}.ant-form-item-has-feedback .ant-switch{margin:2px 0 4px}.ant-form-item-has-warning .ant-form-item-split{color:#faad14}.ant-form-item-has-error .ant-form-item-split{color:#ff4d4f}.ant-form{box-sizing:border-box;margin:0;padding:0;color:rgba(0,0,0,.85);font-size:14px;font-variant:tabular-nums;line-height:1.5715;list-style:none;font-feature-settings:"tnum"}.ant-form legend{display:block;width:100%;margin-bottom:20px;padding:0;color:rgba(0,0,0,.45);font-size:16px;line-height:inherit;border:0;border-bottom:1px solid #d9d9d9}.ant-form label{font-size:14px}.ant-form input[type=search]{box-sizing:border-box}.ant-form input[type=radio],.ant-form input[type=checkbox]{line-height:normal}.ant-form input[type=file]{display:block}.ant-form input[type=range]{display:block;width:100%}.ant-form select[multiple],.ant-form select[size]{height:auto}.ant-form input[type=file]:focus,.ant-form input[type=radio]:focus,.ant-form input[type=checkbox]:focus{outline:thin dotted;outline:5px auto -webkit-focus-ring-color;outline-offset:-2px}.ant-form output{display:block;padding-top:15px;color:rgba(0,0,0,.85);font-size:14px;line-height:1.5715}.ant-form .ant-form-text{display:inline-block;padding-right:8px}.ant-form-small .ant-form-item-label>label{height:24px}.ant-form-small .ant-form-item-control-input{min-height:24px}.ant-form-large .ant-form-item-label>label{height:40px}.ant-form-large .ant-form-item-control-input{min-height:40px}.ant-form-item{box-sizing:border-box;margin:0;padding:0;color:rgba(0,0,0,.85);font-size:14px;font-variant:tabular-nums;line-height:1.5715;list-style:none;font-feature-settings:"tnum";margin-bottom:24px;vertical-align:top}.ant-form-item-with-help{transition:none}.ant-form-item-hidden,.ant-form-item-hidden.ant-row{display:none}.ant-form-item-label{display:inline-block;flex-grow:0;overflow:hidden;white-space:nowrap;text-align:right;vertical-align:middle}.ant-form-item-label-left{text-align:left}.ant-form-item-label-wrap{overflow:unset;line-height:1.3215em;white-space:unset}.ant-form-item-label>label{position:relative;display:inline-flex;align-items:center;max-width:100%;height:32px;color:rgba(0,0,0,.85);font-size:14px}.ant-form-item-label>label>.anticon{font-size:14px;vertical-align:top}.ant-form-item-label>label.ant-form-item-required:not(.ant-form-item-required-mark-optional)::before{display:inline-block;margin-right:4px;color:#ff4d4f;font-size:14px;font-family:SimSun,sans-serif;line-height:1;content:"*"}.ant-form-hide-required-mark .ant-form-item-label>label.ant-form-item-required:not(.ant-form-item-required-mark-optional)::before{display:none}.ant-form-item-label>label .ant-form-item-optional{display:inline-block;margin-left:4px;color:rgba(0,0,0,.45)}.ant-form-hide-required-mark .ant-form-item-label>label .ant-form-item-optional{display:none}.ant-form-item-label>label .ant-form-item-tooltip{color:rgba(0,0,0,.45);cursor:help;-ms-writing-mode:lr-tb;writing-mode:horizontal-tb;-webkit-margin-start:4px;margin-inline-start:4px}.ant-form-item-label>label::after{content:":";position:relative;top:-0.5px;margin:0 8px 0 2px}.ant-form-item-label>label.ant-form-item-no-colon::after{content:" "}.ant-form-item-control{display:flex;flex-direction:column;flex-grow:1}.ant-form-item-control:first-child:not([class^=ant-col-]):not([class*=" ant-col-"]){width:100%}.ant-form-item-control-input{position:relative;display:flex;align-items:center;min-height:32px}.ant-form-item-control-input-content{flex:auto;max-width:100%}.ant-form-item-explain,.ant-form-item-extra{clear:both;color:rgba(0,0,0,.45);font-size:14px;line-height:1.5715;transition:color .3s cubic-bezier(0.215, 0.61, 0.355, 1)}.ant-form-item-explain-connected{width:100%}.ant-form-item-extra{min-height:24px}.ant-form-item-with-help .ant-form-item-explain{height:auto;opacity:1}.ant-form-item-feedback-icon{font-size:14px;text-align:center;visibility:visible;animation:zoomIn .3s cubic-bezier(0.12, 0.4, 0.29, 1.46);pointer-events:none}.ant-form-item-feedback-icon-success{color:#52c41a}.ant-form-item-feedback-icon-error{color:#ff4d4f}.ant-form-item-feedback-icon-warning{color:#faad14}.ant-form-item-feedback-icon-validating{color:#1890ff}.ant-show-help{transition:opacity .3s cubic-bezier(0.645, 0.045, 0.355, 1)}.ant-show-help-appear,.ant-show-help-enter{opacity:0}.ant-show-help-appear-active,.ant-show-help-enter-active{opacity:1}.ant-show-help-leave{opacity:1}.ant-show-help-leave-active{opacity:0}.ant-show-help-item{overflow:hidden;transition:height .3s cubic-bezier(0.645, 0.045, 0.355, 1),opacity .3s cubic-bezier(0.645, 0.045, 0.355, 1),transform .3s cubic-bezier(0.645, 0.045, 0.355, 1) !important}.ant-show-help-item-appear,.ant-show-help-item-enter{transform:translateY(-5px);opacity:0}.ant-show-help-item-appear-active,.ant-show-help-item-enter-active{transform:translateY(0);opacity:1}.ant-show-help-item-leave{transition:height .2s cubic-bezier(0.645, 0.045, 0.355, 1),opacity .2s cubic-bezier(0.645, 0.045, 0.355, 1),transform .2s cubic-bezier(0.645, 0.045, 0.355, 1) !important}.ant-show-help-item-leave-active{transform:translateY(-5px)}@keyframes diffZoomIn1{0%{transform:scale(0);opacity:0}100%{transform:scale(1);opacity:1}}@keyframes diffZoomIn2{0%{transform:scale(0);opacity:0}100%{transform:scale(1);opacity:1}}@keyframes diffZoomIn3{0%{transform:scale(0);opacity:0}100%{transform:scale(1);opacity:1}}.ant-form-rtl{direction:rtl}.ant-form-rtl .ant-form-item-label{text-align:left}.ant-form-rtl .ant-form-item-label>label.ant-form-item-required::before{margin-right:0;margin-left:4px}.ant-form-rtl .ant-form-item-label>label::after{margin:0 2px 0 8px}.ant-form-rtl .ant-form-item-label>label .ant-form-item-optional{margin-right:4px;margin-left:0}.ant-col-rtl .ant-form-item-control:first-child{width:100%}.ant-form-rtl .ant-form-item-has-feedback .ant-input{padding-right:11px;padding-left:24px}.ant-form-rtl .ant-form-item-has-feedback .ant-input-affix-wrapper .ant-input-suffix{padding-right:11px;padding-left:18px}.ant-form-rtl .ant-form-item-has-feedback .ant-input-affix-wrapper .ant-input{padding:0}.ant-form-rtl .ant-form-item-has-feedback .ant-input-number-affix-wrapper .ant-input-number{padding:0}.ant-form-rtl .ant-form-item-has-feedback .ant-input-search:not(.ant-input-search-enter-button) .ant-input-suffix{right:auto;left:28px}.ant-form-rtl .ant-form-item-has-feedback .ant-input-number{padding-left:18px}.ant-form-rtl .ant-form-item-has-feedback>.ant-select .ant-select-arrow,.ant-form-rtl .ant-form-item-has-feedback>.ant-select .ant-select-clear,.ant-form-rtl .ant-form-item-has-feedback :not(.ant-input-group-addon)>.ant-select .ant-select-arrow,.ant-form-rtl .ant-form-item-has-feedback :not(.ant-input-group-addon)>.ant-select .ant-select-clear,.ant-form-rtl .ant-form-item-has-feedback :not(.ant-input-number-group-addon)>.ant-select .ant-select-arrow,.ant-form-rtl .ant-form-item-has-feedback :not(.ant-input-number-group-addon)>.ant-select .ant-select-clear{right:auto;left:32px}.ant-form-rtl .ant-form-item-has-feedback>.ant-select .ant-select-selection-selected-value,.ant-form-rtl .ant-form-item-has-feedback :not(.ant-input-group-addon)>.ant-select .ant-select-selection-selected-value,.ant-form-rtl .ant-form-item-has-feedback :not(.ant-input-number-group-addon)>.ant-select .ant-select-selection-selected-value{padding-right:0;padding-left:42px}.ant-form-rtl .ant-form-item-has-feedback .ant-cascader-picker-arrow{margin-right:0;margin-left:19px}.ant-form-rtl .ant-form-item-has-feedback .ant-cascader-picker-clear{right:auto;left:32px}.ant-form-rtl .ant-form-item-has-feedback .ant-picker{padding-right:11px;padding-left:29.2px}.ant-form-rtl .ant-form-item-has-feedback .ant-picker-large{padding-right:11px;padding-left:29.2px}.ant-form-rtl .ant-form-item-has-feedback .ant-picker-small{padding-right:7px;padding-left:25.2px}.ant-form-rtl .ant-form-item-has-feedback.ant-form-item-has-success .ant-form-item-children-icon,.ant-form-rtl .ant-form-item-has-feedback.ant-form-item-has-warning .ant-form-item-children-icon,.ant-form-rtl .ant-form-item-has-feedback.ant-form-item-has-error .ant-form-item-children-icon,.ant-form-rtl .ant-form-item-has-feedback.ant-form-item-is-validating .ant-form-item-children-icon{right:auto;left:0}.ant-form-rtl.ant-form-inline .ant-form-item{margin-right:0;margin-left:16px}</style><style>.ant-row{display:flex;flex-flow:row wrap;min-width:0}.ant-row::before,.ant-row::after{display:flex}.ant-row-no-wrap{flex-wrap:nowrap}.ant-row-start{justify-content:flex-start}.ant-row-center{justify-content:center}.ant-row-end{justify-content:flex-end}.ant-row-space-between{justify-content:space-between}.ant-row-space-around{justify-content:space-around}.ant-row-space-evenly{justify-content:space-evenly}.ant-row-top{align-items:flex-start}.ant-row-middle{align-items:center}.ant-row-bottom{align-items:flex-end}.ant-col{position:relative;max-width:100%;min-height:1px}.ant-col-24{display:block;flex:0 0 100%;max-width:100%}.ant-col-push-24{left:100%}.ant-col-pull-24{right:100%}.ant-col-offset-24{margin-left:100%}.ant-col-order-24{order:24}.ant-col-23{display:block;flex:0 0 95.83333333%;max-width:95.83333333%}.ant-col-push-23{left:95.83333333%}.ant-col-pull-23{right:95.83333333%}.ant-col-offset-23{margin-left:95.83333333%}.ant-col-order-23{order:23}.ant-col-22{display:block;flex:0 0 91.66666667%;max-width:91.66666667%}.ant-col-push-22{left:91.66666667%}.ant-col-pull-22{right:91.66666667%}.ant-col-offset-22{margin-left:91.66666667%}.ant-col-order-22{order:22}.ant-col-21{display:block;flex:0 0 87.5%;max-width:87.5%}.ant-col-push-21{left:87.5%}.ant-col-pull-21{right:87.5%}.ant-col-offset-21{margin-left:87.5%}.ant-col-order-21{order:21}.ant-col-20{display:block;flex:0 0 83.33333333%;max-width:83.33333333%}.ant-col-push-20{left:83.33333333%}.ant-col-pull-20{right:83.33333333%}.ant-col-offset-20{margin-left:83.33333333%}.ant-col-order-20{order:20}.ant-col-19{display:block;flex:0 0 79.16666667%;max-width:79.16666667%}.ant-col-push-19{left:79.16666667%}.ant-col-pull-19{right:79.16666667%}.ant-col-offset-19{margin-left:79.16666667%}.ant-col-order-19{order:19}.ant-col-18{display:block;flex:0 0 75%;max-width:75%}.ant-col-push-18{left:75%}.ant-col-pull-18{right:75%}.ant-col-offset-18{margin-left:75%}.ant-col-order-18{order:18}.ant-col-17{display:block;flex:0 0 70.83333333%;max-width:70.83333333%}.ant-col-push-17{left:70.83333333%}.ant-col-pull-17{right:70.83333333%}.ant-col-offset-17{margin-left:70.83333333%}.ant-col-order-17{order:17}.ant-col-16{display:block;flex:0 0 66.66666667%;max-width:66.66666667%}.ant-col-push-16{left:66.66666667%}.ant-col-pull-16{right:66.66666667%}.ant-col-offset-16{margin-left:66.66666667%}.ant-col-order-16{order:16}.ant-col-15{display:block;flex:0 0 62.5%;max-width:62.5%}.ant-col-push-15{left:62.5%}.ant-col-pull-15{right:62.5%}.ant-col-offset-15{margin-left:62.5%}.ant-col-order-15{order:15}.ant-col-14{display:block;flex:0 0 58.33333333%;max-width:58.33333333%}.ant-col-push-14{left:58.33333333%}.ant-col-pull-14{right:58.33333333%}.ant-col-offset-14{margin-left:58.33333333%}.ant-col-order-14{order:14}.ant-col-13{display:block;flex:0 0 54.16666667%;max-width:54.16666667%}.ant-col-push-13{left:54.16666667%}.ant-col-pull-13{right:54.16666667%}.ant-col-offset-13{margin-left:54.16666667%}.ant-col-order-13{order:13}.ant-col-12{display:block;flex:0 0 50%;max-width:50%}.ant-col-push-12{left:50%}.ant-col-pull-12{right:50%}.ant-col-offset-12{margin-left:50%}.ant-col-order-12{order:12}.ant-col-11{display:block;flex:0 0 45.83333333%;max-width:45.83333333%}.ant-col-push-11{left:45.83333333%}.ant-col-pull-11{right:45.83333333%}.ant-col-offset-11{margin-left:45.83333333%}.ant-col-order-11{order:11}.ant-col-10{display:block;flex:0 0 41.66666667%;max-width:41.66666667%}.ant-col-push-10{left:41.66666667%}.ant-col-pull-10{right:41.66666667%}.ant-col-offset-10{margin-left:41.66666667%}.ant-col-order-10{order:10}.ant-col-9{display:block;flex:0 0 37.5%;max-width:37.5%}.ant-col-push-9{left:37.5%}.ant-col-pull-9{right:37.5%}.ant-col-offset-9{margin-left:37.5%}.ant-col-order-9{order:9}.ant-col-8{display:block;flex:0 0 33.33333333%;max-width:33.33333333%}.ant-col-push-8{left:33.33333333%}.ant-col-pull-8{right:33.33333333%}.ant-col-offset-8{margin-left:33.33333333%}.ant-col-order-8{order:8}.ant-col-7{display:block;flex:0 0 29.16666667%;max-width:29.16666667%}.ant-col-push-7{left:29.16666667%}.ant-col-pull-7{right:29.16666667%}.ant-col-offset-7{margin-left:29.16666667%}.ant-col-order-7{order:7}.ant-col-6{display:block;flex:0 0 25%;max-width:25%}.ant-col-push-6{left:25%}.ant-col-pull-6{right:25%}.ant-col-offset-6{margin-left:25%}.ant-col-order-6{order:6}.ant-col-5{display:block;flex:0 0 20.83333333%;max-width:20.83333333%}.ant-col-push-5{left:20.83333333%}.ant-col-pull-5{right:20.83333333%}.ant-col-offset-5{margin-left:20.83333333%}.ant-col-order-5{order:5}.ant-col-4{display:block;flex:0 0 16.66666667%;max-width:16.66666667%}.ant-col-push-4{left:16.66666667%}.ant-col-pull-4{right:16.66666667%}.ant-col-offset-4{margin-left:16.66666667%}.ant-col-order-4{order:4}.ant-col-3{display:block;flex:0 0 12.5%;max-width:12.5%}.ant-col-push-3{left:12.5%}.ant-col-pull-3{right:12.5%}.ant-col-offset-3{margin-left:12.5%}.ant-col-order-3{order:3}.ant-col-2{display:block;flex:0 0 8.33333333%;max-width:8.33333333%}.ant-col-push-2{left:8.33333333%}.ant-col-pull-2{right:8.33333333%}.ant-col-offset-2{margin-left:8.33333333%}.ant-col-order-2{order:2}.ant-col-1{display:block;flex:0 0 4.16666667%;max-width:4.16666667%}.ant-col-push-1{left:4.16666667%}.ant-col-pull-1{right:4.16666667%}.ant-col-offset-1{margin-left:4.16666667%}.ant-col-order-1{order:1}.ant-col-0{display:none}.ant-col-push-0{left:auto}.ant-col-pull-0{right:auto}.ant-col-push-0{left:auto}.ant-col-pull-0{right:auto}.ant-col-offset-0{margin-left:0}.ant-col-order-0{order:0}.ant-col-push-0.ant-col-rtl{right:auto}.ant-col-pull-0.ant-col-rtl{left:auto}.ant-col-push-0.ant-col-rtl{right:auto}.ant-col-pull-0.ant-col-rtl{left:auto}.ant-col-offset-0.ant-col-rtl{margin-right:0}.ant-col-push-1.ant-col-rtl{right:4.16666667%;left:auto}.ant-col-pull-1.ant-col-rtl{right:auto;left:4.16666667%}.ant-col-offset-1.ant-col-rtl{margin-right:4.16666667%;margin-left:0}.ant-col-push-2.ant-col-rtl{right:8.33333333%;left:auto}.ant-col-pull-2.ant-col-rtl{right:auto;left:8.33333333%}.ant-col-offset-2.ant-col-rtl{margin-right:8.33333333%;margin-left:0}.ant-col-push-3.ant-col-rtl{right:12.5%;left:auto}.ant-col-pull-3.ant-col-rtl{right:auto;left:12.5%}.ant-col-offset-3.ant-col-rtl{margin-right:12.5%;margin-left:0}.ant-col-push-4.ant-col-rtl{right:16.66666667%;left:auto}.ant-col-pull-4.ant-col-rtl{right:auto;left:16.66666667%}.ant-col-offset-4.ant-col-rtl{margin-right:16.66666667%;margin-left:0}.ant-col-push-5.ant-col-rtl{right:20.83333333%;left:auto}.ant-col-pull-5.ant-col-rtl{right:auto;left:20.83333333%}.ant-col-offset-5.ant-col-rtl{margin-right:20.83333333%;margin-left:0}.ant-col-push-6.ant-col-rtl{right:25%;left:auto}.ant-col-pull-6.ant-col-rtl{right:auto;left:25%}.ant-col-offset-6.ant-col-rtl{margin-right:25%;margin-left:0}.ant-col-push-7.ant-col-rtl{right:29.16666667%;left:auto}.ant-col-pull-7.ant-col-rtl{right:auto;left:29.16666667%}.ant-col-offset-7.ant-col-rtl{margin-right:29.16666667%;margin-left:0}.ant-col-push-8.ant-col-rtl{right:33.33333333%;left:auto}.ant-col-pull-8.ant-col-rtl{right:auto;left:33.33333333%}.ant-col-offset-8.ant-col-rtl{margin-right:33.33333333%;margin-left:0}.ant-col-push-9.ant-col-rtl{right:37.5%;left:auto}.ant-col-pull-9.ant-col-rtl{right:auto;left:37.5%}.ant-col-offset-9.ant-col-rtl{margin-right:37.5%;margin-left:0}.ant-col-push-10.ant-col-rtl{right:41.66666667%;left:auto}.ant-col-pull-10.ant-col-rtl{right:auto;left:41.66666667%}.ant-col-offset-10.ant-col-rtl{margin-right:41.66666667%;margin-left:0}.ant-col-push-11.ant-col-rtl{right:45.83333333%;left:auto}.ant-col-pull-11.ant-col-rtl{right:auto;left:45.83333333%}.ant-col-offset-11.ant-col-rtl{margin-right:45.83333333%;margin-left:0}.ant-col-push-12.ant-col-rtl{right:50%;left:auto}.ant-col-pull-12.ant-col-rtl{right:auto;left:50%}.ant-col-offset-12.ant-col-rtl{margin-right:50%;margin-left:0}.ant-col-push-13.ant-col-rtl{right:54.16666667%;left:auto}.ant-col-pull-13.ant-col-rtl{right:auto;left:54.16666667%}.ant-col-offset-13.ant-col-rtl{margin-right:54.16666667%;margin-left:0}.ant-col-push-14.ant-col-rtl{right:58.33333333%;left:auto}.ant-col-pull-14.ant-col-rtl{right:auto;left:58.33333333%}.ant-col-offset-14.ant-col-rtl{margin-right:58.33333333%;margin-left:0}.ant-col-push-15.ant-col-rtl{right:62.5%;left:auto}.ant-col-pull-15.ant-col-rtl{right:auto;left:62.5%}.ant-col-offset-15.ant-col-rtl{margin-right:62.5%;margin-left:0}.ant-col-push-16.ant-col-rtl{right:66.66666667%;left:auto}.ant-col-pull-16.ant-col-rtl{right:auto;left:66.66666667%}.ant-col-offset-16.ant-col-rtl{margin-right:66.66666667%;margin-left:0}.ant-col-push-17.ant-col-rtl{right:70.83333333%;left:auto}.ant-col-pull-17.ant-col-rtl{right:auto;left:70.83333333%}.ant-col-offset-17.ant-col-rtl{margin-right:70.83333333%;margin-left:0}.ant-col-push-18.ant-col-rtl{right:75%;left:auto}.ant-col-pull-18.ant-col-rtl{right:auto;left:75%}.ant-col-offset-18.ant-col-rtl{margin-right:75%;margin-left:0}.ant-col-push-19.ant-col-rtl{right:79.16666667%;left:auto}.ant-col-pull-19.ant-col-rtl{right:auto;left:79.16666667%}.ant-col-offset-19.ant-col-rtl{margin-right:79.16666667%;margin-left:0}.ant-col-push-20.ant-col-rtl{right:83.33333333%;left:auto}.ant-col-pull-20.ant-col-rtl{right:auto;left:83.33333333%}.ant-col-offset-20.ant-col-rtl{margin-right:83.33333333%;margin-left:0}.ant-col-push-21.ant-col-rtl{right:87.5%;left:auto}.ant-col-pull-21.ant-col-rtl{right:auto;left:87.5%}.ant-col-offset-21.ant-col-rtl{margin-right:87.5%;margin-left:0}.ant-col-push-22.ant-col-rtl{right:91.66666667%;left:auto}.ant-col-pull-22.ant-col-rtl{right:auto;left:91.66666667%}.ant-col-offset-22.ant-col-rtl{margin-right:91.66666667%;margin-left:0}.ant-col-push-23.ant-col-rtl{right:95.83333333%;left:auto}.ant-col-pull-23.ant-col-rtl{right:auto;left:95.83333333%}.ant-col-offset-23.ant-col-rtl{margin-right:95.83333333%;margin-left:0}.ant-col-push-24.ant-col-rtl{right:100%;left:auto}.ant-col-pull-24.ant-col-rtl{right:auto;left:100%}.ant-col-offset-24.ant-col-rtl{margin-right:100%;margin-left:0}.ant-col-xs-24{display:block;flex:0 0 100%;max-width:100%}.ant-col-xs-push-24{left:100%}.ant-col-xs-pull-24{right:100%}.ant-col-xs-offset-24{margin-left:100%}.ant-col-xs-order-24{order:24}.ant-col-xs-23{display:block;flex:0 0 95.83333333%;max-width:95.83333333%}.ant-col-xs-push-23{left:95.83333333%}.ant-col-xs-pull-23{right:95.83333333%}.ant-col-xs-offset-23{margin-left:95.83333333%}.ant-col-xs-order-23{order:23}.ant-col-xs-22{display:block;flex:0 0 91.66666667%;max-width:91.66666667%}.ant-col-xs-push-22{left:91.66666667%}.ant-col-xs-pull-22{right:91.66666667%}.ant-col-xs-offset-22{margin-left:91.66666667%}.ant-col-xs-order-22{order:22}.ant-col-xs-21{display:block;flex:0 0 87.5%;max-width:87.5%}.ant-col-xs-push-21{left:87.5%}.ant-col-xs-pull-21{right:87.5%}.ant-col-xs-offset-21{margin-left:87.5%}.ant-col-xs-order-21{order:21}.ant-col-xs-20{display:block;flex:0 0 83.33333333%;max-width:83.33333333%}.ant-col-xs-push-20{left:83.33333333%}.ant-col-xs-pull-20{right:83.33333333%}.ant-col-xs-offset-20{margin-left:83.33333333%}.ant-col-xs-order-20{order:20}.ant-col-xs-19{display:block;flex:0 0 79.16666667%;max-width:79.16666667%}.ant-col-xs-push-19{left:79.16666667%}.ant-col-xs-pull-19{right:79.16666667%}.ant-col-xs-offset-19{margin-left:79.16666667%}.ant-col-xs-order-19{order:19}.ant-col-xs-18{display:block;flex:0 0 75%;max-width:75%}.ant-col-xs-push-18{left:75%}.ant-col-xs-pull-18{right:75%}.ant-col-xs-offset-18{margin-left:75%}.ant-col-xs-order-18{order:18}.ant-col-xs-17{display:block;flex:0 0 70.83333333%;max-width:70.83333333%}.ant-col-xs-push-17{left:70.83333333%}.ant-col-xs-pull-17{right:70.83333333%}.ant-col-xs-offset-17{margin-left:70.83333333%}.ant-col-xs-order-17{order:17}.ant-col-xs-16{display:block;flex:0 0 66.66666667%;max-width:66.66666667%}.ant-col-xs-push-16{left:66.66666667%}.ant-col-xs-pull-16{right:66.66666667%}.ant-col-xs-offset-16{margin-left:66.66666667%}.ant-col-xs-order-16{order:16}.ant-col-xs-15{display:block;flex:0 0 62.5%;max-width:62.5%}.ant-col-xs-push-15{left:62.5%}.ant-col-xs-pull-15{right:62.5%}.ant-col-xs-offset-15{margin-left:62.5%}.ant-col-xs-order-15{order:15}.ant-col-xs-14{display:block;flex:0 0 58.33333333%;max-width:58.33333333%}.ant-col-xs-push-14{left:58.33333333%}.ant-col-xs-pull-14{right:58.33333333%}.ant-col-xs-offset-14{margin-left:58.33333333%}.ant-col-xs-order-14{order:14}.ant-col-xs-13{display:block;flex:0 0 54.16666667%;max-width:54.16666667%}.ant-col-xs-push-13{left:54.16666667%}.ant-col-xs-pull-13{right:54.16666667%}.ant-col-xs-offset-13{margin-left:54.16666667%}.ant-col-xs-order-13{order:13}.ant-col-xs-12{display:block;flex:0 0 50%;max-width:50%}.ant-col-xs-push-12{left:50%}.ant-col-xs-pull-12{right:50%}.ant-col-xs-offset-12{margin-left:50%}.ant-col-xs-order-12{order:12}.ant-col-xs-11{display:block;flex:0 0 45.83333333%;max-width:45.83333333%}.ant-col-xs-push-11{left:45.83333333%}.ant-col-xs-pull-11{right:45.83333333%}.ant-col-xs-offset-11{margin-left:45.83333333%}.ant-col-xs-order-11{order:11}.ant-col-xs-10{display:block;flex:0 0 41.66666667%;max-width:41.66666667%}.ant-col-xs-push-10{left:41.66666667%}.ant-col-xs-pull-10{right:41.66666667%}.ant-col-xs-offset-10{margin-left:41.66666667%}.ant-col-xs-order-10{order:10}.ant-col-xs-9{display:block;flex:0 0 37.5%;max-width:37.5%}.ant-col-xs-push-9{left:37.5%}.ant-col-xs-pull-9{right:37.5%}.ant-col-xs-offset-9{margin-left:37.5%}.ant-col-xs-order-9{order:9}.ant-col-xs-8{display:block;flex:0 0 33.33333333%;max-width:33.33333333%}.ant-col-xs-push-8{left:33.33333333%}.ant-col-xs-pull-8{right:33.33333333%}.ant-col-xs-offset-8{margin-left:33.33333333%}.ant-col-xs-order-8{order:8}.ant-col-xs-7{display:block;flex:0 0 29.16666667%;max-width:29.16666667%}.ant-col-xs-push-7{left:29.16666667%}.ant-col-xs-pull-7{right:29.16666667%}.ant-col-xs-offset-7{margin-left:29.16666667%}.ant-col-xs-order-7{order:7}.ant-col-xs-6{display:block;flex:0 0 25%;max-width:25%}.ant-col-xs-push-6{left:25%}.ant-col-xs-pull-6{right:25%}.ant-col-xs-offset-6{margin-left:25%}.ant-col-xs-order-6{order:6}.ant-col-xs-5{display:block;flex:0 0 20.83333333%;max-width:20.83333333%}.ant-col-xs-push-5{left:20.83333333%}.ant-col-xs-pull-5{right:20.83333333%}.ant-col-xs-offset-5{margin-left:20.83333333%}.ant-col-xs-order-5{order:5}.ant-col-xs-4{display:block;flex:0 0 16.66666667%;max-width:16.66666667%}.ant-col-xs-push-4{left:16.66666667%}.ant-col-xs-pull-4{right:16.66666667%}.ant-col-xs-offset-4{margin-left:16.66666667%}.ant-col-xs-order-4{order:4}.ant-col-xs-3{display:block;flex:0 0 12.5%;max-width:12.5%}.ant-col-xs-push-3{left:12.5%}.ant-col-xs-pull-3{right:12.5%}.ant-col-xs-offset-3{margin-left:12.5%}.ant-col-xs-order-3{order:3}.ant-col-xs-2{display:block;flex:0 0 8.33333333%;max-width:8.33333333%}.ant-col-xs-push-2{left:8.33333333%}.ant-col-xs-pull-2{right:8.33333333%}.ant-col-xs-offset-2{margin-left:8.33333333%}.ant-col-xs-order-2{order:2}.ant-col-xs-1{display:block;flex:0 0 4.16666667%;max-width:4.16666667%}.ant-col-xs-push-1{left:4.16666667%}.ant-col-xs-pull-1{right:4.16666667%}.ant-col-xs-offset-1{margin-left:4.16666667%}.ant-col-xs-order-1{order:1}.ant-col-xs-0{display:none}.ant-col-push-0{left:auto}.ant-col-pull-0{right:auto}.ant-col-xs-push-0{left:auto}.ant-col-xs-pull-0{right:auto}.ant-col-xs-offset-0{margin-left:0}.ant-col-xs-order-0{order:0}.ant-col-push-0.ant-col-rtl{right:auto}.ant-col-pull-0.ant-col-rtl{left:auto}.ant-col-xs-push-0.ant-col-rtl{right:auto}.ant-col-xs-pull-0.ant-col-rtl{left:auto}.ant-col-xs-offset-0.ant-col-rtl{margin-right:0}.ant-col-xs-push-1.ant-col-rtl{right:4.16666667%;left:auto}.ant-col-xs-pull-1.ant-col-rtl{right:auto;left:4.16666667%}.ant-col-xs-offset-1.ant-col-rtl{margin-right:4.16666667%;margin-left:0}.ant-col-xs-push-2.ant-col-rtl{right:8.33333333%;left:auto}.ant-col-xs-pull-2.ant-col-rtl{right:auto;left:8.33333333%}.ant-col-xs-offset-2.ant-col-rtl{margin-right:8.33333333%;margin-left:0}.ant-col-xs-push-3.ant-col-rtl{right:12.5%;left:auto}.ant-col-xs-pull-3.ant-col-rtl{right:auto;left:12.5%}.ant-col-xs-offset-3.ant-col-rtl{margin-right:12.5%;margin-left:0}.ant-col-xs-push-4.ant-col-rtl{right:16.66666667%;left:auto}.ant-col-xs-pull-4.ant-col-rtl{right:auto;left:16.66666667%}.ant-col-xs-offset-4.ant-col-rtl{margin-right:16.66666667%;margin-left:0}.ant-col-xs-push-5.ant-col-rtl{right:20.83333333%;left:auto}.ant-col-xs-pull-5.ant-col-rtl{right:auto;left:20.83333333%}.ant-col-xs-offset-5.ant-col-rtl{margin-right:20.83333333%;margin-left:0}.ant-col-xs-push-6.ant-col-rtl{right:25%;left:auto}.ant-col-xs-pull-6.ant-col-rtl{right:auto;left:25%}.ant-col-xs-offset-6.ant-col-rtl{margin-right:25%;margin-left:0}.ant-col-xs-push-7.ant-col-rtl{right:29.16666667%;left:auto}.ant-col-xs-pull-7.ant-col-rtl{right:auto;left:29.16666667%}.ant-col-xs-offset-7.ant-col-rtl{margin-right:29.16666667%;margin-left:0}.ant-col-xs-push-8.ant-col-rtl{right:33.33333333%;left:auto}.ant-col-xs-pull-8.ant-col-rtl{right:auto;left:33.33333333%}.ant-col-xs-offset-8.ant-col-rtl{margin-right:33.33333333%;margin-left:0}.ant-col-xs-push-9.ant-col-rtl{right:37.5%;left:auto}.ant-col-xs-pull-9.ant-col-rtl{right:auto;left:37.5%}.ant-col-xs-offset-9.ant-col-rtl{margin-right:37.5%;margin-left:0}.ant-col-xs-push-10.ant-col-rtl{right:41.66666667%;left:auto}.ant-col-xs-pull-10.ant-col-rtl{right:auto;left:41.66666667%}.ant-col-xs-offset-10.ant-col-rtl{margin-right:41.66666667%;margin-left:0}.ant-col-xs-push-11.ant-col-rtl{right:45.83333333%;left:auto}.ant-col-xs-pull-11.ant-col-rtl{right:auto;left:45.83333333%}.ant-col-xs-offset-11.ant-col-rtl{margin-right:45.83333333%;margin-left:0}.ant-col-xs-push-12.ant-col-rtl{right:50%;left:auto}.ant-col-xs-pull-12.ant-col-rtl{right:auto;left:50%}.ant-col-xs-offset-12.ant-col-rtl{margin-right:50%;margin-left:0}.ant-col-xs-push-13.ant-col-rtl{right:54.16666667%;left:auto}.ant-col-xs-pull-13.ant-col-rtl{right:auto;left:54.16666667%}.ant-col-xs-offset-13.ant-col-rtl{margin-right:54.16666667%;margin-left:0}.ant-col-xs-push-14.ant-col-rtl{right:58.33333333%;left:auto}.ant-col-xs-pull-14.ant-col-rtl{right:auto;left:58.33333333%}.ant-col-xs-offset-14.ant-col-rtl{margin-right:58.33333333%;margin-left:0}.ant-col-xs-push-15.ant-col-rtl{right:62.5%;left:auto}.ant-col-xs-pull-15.ant-col-rtl{right:auto;left:62.5%}.ant-col-xs-offset-15.ant-col-rtl{margin-right:62.5%;margin-left:0}.ant-col-xs-push-16.ant-col-rtl{right:66.66666667%;left:auto}.ant-col-xs-pull-16.ant-col-rtl{right:auto;left:66.66666667%}.ant-col-xs-offset-16.ant-col-rtl{margin-right:66.66666667%;margin-left:0}.ant-col-xs-push-17.ant-col-rtl{right:70.83333333%;left:auto}.ant-col-xs-pull-17.ant-col-rtl{right:auto;left:70.83333333%}.ant-col-xs-offset-17.ant-col-rtl{margin-right:70.83333333%;margin-left:0}.ant-col-xs-push-18.ant-col-rtl{right:75%;left:auto}.ant-col-xs-pull-18.ant-col-rtl{right:auto;left:75%}.ant-col-xs-offset-18.ant-col-rtl{margin-right:75%;margin-left:0}.ant-col-xs-push-19.ant-col-rtl{right:79.16666667%;left:auto}.ant-col-xs-pull-19.ant-col-rtl{right:auto;left:79.16666667%}.ant-col-xs-offset-19.ant-col-rtl{margin-right:79.16666667%;margin-left:0}.ant-col-xs-push-20.ant-col-rtl{right:83.33333333%;left:auto}.ant-col-xs-pull-20.ant-col-rtl{right:auto;left:83.33333333%}.ant-col-xs-offset-20.ant-col-rtl{margin-right:83.33333333%;margin-left:0}.ant-col-xs-push-21.ant-col-rtl{right:87.5%;left:auto}.ant-col-xs-pull-21.ant-col-rtl{right:auto;left:87.5%}.ant-col-xs-offset-21.ant-col-rtl{margin-right:87.5%;margin-left:0}.ant-col-xs-push-22.ant-col-rtl{right:91.66666667%;left:auto}.ant-col-xs-pull-22.ant-col-rtl{right:auto;left:91.66666667%}.ant-col-xs-offset-22.ant-col-rtl{margin-right:91.66666667%;margin-left:0}.ant-col-xs-push-23.ant-col-rtl{right:95.83333333%;left:auto}.ant-col-xs-pull-23.ant-col-rtl{right:auto;left:95.83333333%}.ant-col-xs-offset-23.ant-col-rtl{margin-right:95.83333333%;margin-left:0}.ant-col-xs-push-24.ant-col-rtl{right:100%;left:auto}.ant-col-xs-pull-24.ant-col-rtl{right:auto;left:100%}.ant-col-xs-offset-24.ant-col-rtl{margin-right:100%;margin-left:0}@media(min-width: 576px){.ant-col-sm-24{display:block;flex:0 0 100%;max-width:100%}.ant-col-sm-push-24{left:100%}.ant-col-sm-pull-24{right:100%}.ant-col-sm-offset-24{margin-left:100%}.ant-col-sm-order-24{order:24}.ant-col-sm-23{display:block;flex:0 0 95.83333333%;max-width:95.83333333%}.ant-col-sm-push-23{left:95.83333333%}.ant-col-sm-pull-23{right:95.83333333%}.ant-col-sm-offset-23{margin-left:95.83333333%}.ant-col-sm-order-23{order:23}.ant-col-sm-22{display:block;flex:0 0 91.66666667%;max-width:91.66666667%}.ant-col-sm-push-22{left:91.66666667%}.ant-col-sm-pull-22{right:91.66666667%}.ant-col-sm-offset-22{margin-left:91.66666667%}.ant-col-sm-order-22{order:22}.ant-col-sm-21{display:block;flex:0 0 87.5%;max-width:87.5%}.ant-col-sm-push-21{left:87.5%}.ant-col-sm-pull-21{right:87.5%}.ant-col-sm-offset-21{margin-left:87.5%}.ant-col-sm-order-21{order:21}.ant-col-sm-20{display:block;flex:0 0 83.33333333%;max-width:83.33333333%}.ant-col-sm-push-20{left:83.33333333%}.ant-col-sm-pull-20{right:83.33333333%}.ant-col-sm-offset-20{margin-left:83.33333333%}.ant-col-sm-order-20{order:20}.ant-col-sm-19{display:block;flex:0 0 79.16666667%;max-width:79.16666667%}.ant-col-sm-push-19{left:79.16666667%}.ant-col-sm-pull-19{right:79.16666667%}.ant-col-sm-offset-19{margin-left:79.16666667%}.ant-col-sm-order-19{order:19}.ant-col-sm-18{display:block;flex:0 0 75%;max-width:75%}.ant-col-sm-push-18{left:75%}.ant-col-sm-pull-18{right:75%}.ant-col-sm-offset-18{margin-left:75%}.ant-col-sm-order-18{order:18}.ant-col-sm-17{display:block;flex:0 0 70.83333333%;max-width:70.83333333%}.ant-col-sm-push-17{left:70.83333333%}.ant-col-sm-pull-17{right:70.83333333%}.ant-col-sm-offset-17{margin-left:70.83333333%}.ant-col-sm-order-17{order:17}.ant-col-sm-16{display:block;flex:0 0 66.66666667%;max-width:66.66666667%}.ant-col-sm-push-16{left:66.66666667%}.ant-col-sm-pull-16{right:66.66666667%}.ant-col-sm-offset-16{margin-left:66.66666667%}.ant-col-sm-order-16{order:16}.ant-col-sm-15{display:block;flex:0 0 62.5%;max-width:62.5%}.ant-col-sm-push-15{left:62.5%}.ant-col-sm-pull-15{right:62.5%}.ant-col-sm-offset-15{margin-left:62.5%}.ant-col-sm-order-15{order:15}.ant-col-sm-14{display:block;flex:0 0 58.33333333%;max-width:58.33333333%}.ant-col-sm-push-14{left:58.33333333%}.ant-col-sm-pull-14{right:58.33333333%}.ant-col-sm-offset-14{margin-left:58.33333333%}.ant-col-sm-order-14{order:14}.ant-col-sm-13{display:block;flex:0 0 54.16666667%;max-width:54.16666667%}.ant-col-sm-push-13{left:54.16666667%}.ant-col-sm-pull-13{right:54.16666667%}.ant-col-sm-offset-13{margin-left:54.16666667%}.ant-col-sm-order-13{order:13}.ant-col-sm-12{display:block;flex:0 0 50%;max-width:50%}.ant-col-sm-push-12{left:50%}.ant-col-sm-pull-12{right:50%}.ant-col-sm-offset-12{margin-left:50%}.ant-col-sm-order-12{order:12}.ant-col-sm-11{display:block;flex:0 0 45.83333333%;max-width:45.83333333%}.ant-col-sm-push-11{left:45.83333333%}.ant-col-sm-pull-11{right:45.83333333%}.ant-col-sm-offset-11{margin-left:45.83333333%}.ant-col-sm-order-11{order:11}.ant-col-sm-10{display:block;flex:0 0 41.66666667%;max-width:41.66666667%}.ant-col-sm-push-10{left:41.66666667%}.ant-col-sm-pull-10{right:41.66666667%}.ant-col-sm-offset-10{margin-left:41.66666667%}.ant-col-sm-order-10{order:10}.ant-col-sm-9{display:block;flex:0 0 37.5%;max-width:37.5%}.ant-col-sm-push-9{left:37.5%}.ant-col-sm-pull-9{right:37.5%}.ant-col-sm-offset-9{margin-left:37.5%}.ant-col-sm-order-9{order:9}.ant-col-sm-8{display:block;flex:0 0 33.33333333%;max-width:33.33333333%}.ant-col-sm-push-8{left:33.33333333%}.ant-col-sm-pull-8{right:33.33333333%}.ant-col-sm-offset-8{margin-left:33.33333333%}.ant-col-sm-order-8{order:8}.ant-col-sm-7{display:block;flex:0 0 29.16666667%;max-width:29.16666667%}.ant-col-sm-push-7{left:29.16666667%}.ant-col-sm-pull-7{right:29.16666667%}.ant-col-sm-offset-7{margin-left:29.16666667%}.ant-col-sm-order-7{order:7}.ant-col-sm-6{display:block;flex:0 0 25%;max-width:25%}.ant-col-sm-push-6{left:25%}.ant-col-sm-pull-6{right:25%}.ant-col-sm-offset-6{margin-left:25%}.ant-col-sm-order-6{order:6}.ant-col-sm-5{display:block;flex:0 0 20.83333333%;max-width:20.83333333%}.ant-col-sm-push-5{left:20.83333333%}.ant-col-sm-pull-5{right:20.83333333%}.ant-col-sm-offset-5{margin-left:20.83333333%}.ant-col-sm-order-5{order:5}.ant-col-sm-4{display:block;flex:0 0 16.66666667%;max-width:16.66666667%}.ant-col-sm-push-4{left:16.66666667%}.ant-col-sm-pull-4{right:16.66666667%}.ant-col-sm-offset-4{margin-left:16.66666667%}.ant-col-sm-order-4{order:4}.ant-col-sm-3{display:block;flex:0 0 12.5%;max-width:12.5%}.ant-col-sm-push-3{left:12.5%}.ant-col-sm-pull-3{right:12.5%}.ant-col-sm-offset-3{margin-left:12.5%}.ant-col-sm-order-3{order:3}.ant-col-sm-2{display:block;flex:0 0 8.33333333%;max-width:8.33333333%}.ant-col-sm-push-2{left:8.33333333%}.ant-col-sm-pull-2{right:8.33333333%}.ant-col-sm-offset-2{margin-left:8.33333333%}.ant-col-sm-order-2{order:2}.ant-col-sm-1{display:block;flex:0 0 4.16666667%;max-width:4.16666667%}.ant-col-sm-push-1{left:4.16666667%}.ant-col-sm-pull-1{right:4.16666667%}.ant-col-sm-offset-1{margin-left:4.16666667%}.ant-col-sm-order-1{order:1}.ant-col-sm-0{display:none}.ant-col-push-0{left:auto}.ant-col-pull-0{right:auto}.ant-col-sm-push-0{left:auto}.ant-col-sm-pull-0{right:auto}.ant-col-sm-offset-0{margin-left:0}.ant-col-sm-order-0{order:0}.ant-col-push-0.ant-col-rtl{right:auto}.ant-col-pull-0.ant-col-rtl{left:auto}.ant-col-sm-push-0.ant-col-rtl{right:auto}.ant-col-sm-pull-0.ant-col-rtl{left:auto}.ant-col-sm-offset-0.ant-col-rtl{margin-right:0}.ant-col-sm-push-1.ant-col-rtl{right:4.16666667%;left:auto}.ant-col-sm-pull-1.ant-col-rtl{right:auto;left:4.16666667%}.ant-col-sm-offset-1.ant-col-rtl{margin-right:4.16666667%;margin-left:0}.ant-col-sm-push-2.ant-col-rtl{right:8.33333333%;left:auto}.ant-col-sm-pull-2.ant-col-rtl{right:auto;left:8.33333333%}.ant-col-sm-offset-2.ant-col-rtl{margin-right:8.33333333%;margin-left:0}.ant-col-sm-push-3.ant-col-rtl{right:12.5%;left:auto}.ant-col-sm-pull-3.ant-col-rtl{right:auto;left:12.5%}.ant-col-sm-offset-3.ant-col-rtl{margin-right:12.5%;margin-left:0}.ant-col-sm-push-4.ant-col-rtl{right:16.66666667%;left:auto}.ant-col-sm-pull-4.ant-col-rtl{right:auto;left:16.66666667%}.ant-col-sm-offset-4.ant-col-rtl{margin-right:16.66666667%;margin-left:0}.ant-col-sm-push-5.ant-col-rtl{right:20.83333333%;left:auto}.ant-col-sm-pull-5.ant-col-rtl{right:auto;left:20.83333333%}.ant-col-sm-offset-5.ant-col-rtl{margin-right:20.83333333%;margin-left:0}.ant-col-sm-push-6.ant-col-rtl{right:25%;left:auto}.ant-col-sm-pull-6.ant-col-rtl{right:auto;left:25%}.ant-col-sm-offset-6.ant-col-rtl{margin-right:25%;margin-left:0}.ant-col-sm-push-7.ant-col-rtl{right:29.16666667%;left:auto}.ant-col-sm-pull-7.ant-col-rtl{right:auto;left:29.16666667%}.ant-col-sm-offset-7.ant-col-rtl{margin-right:29.16666667%;margin-left:0}.ant-col-sm-push-8.ant-col-rtl{right:33.33333333%;left:auto}.ant-col-sm-pull-8.ant-col-rtl{right:auto;left:33.33333333%}.ant-col-sm-offset-8.ant-col-rtl{margin-right:33.33333333%;margin-left:0}.ant-col-sm-push-9.ant-col-rtl{right:37.5%;left:auto}.ant-col-sm-pull-9.ant-col-rtl{right:auto;left:37.5%}.ant-col-sm-offset-9.ant-col-rtl{margin-right:37.5%;margin-left:0}.ant-col-sm-push-10.ant-col-rtl{right:41.66666667%;left:auto}.ant-col-sm-pull-10.ant-col-rtl{right:auto;left:41.66666667%}.ant-col-sm-offset-10.ant-col-rtl{margin-right:41.66666667%;margin-left:0}.ant-col-sm-push-11.ant-col-rtl{right:45.83333333%;left:auto}.ant-col-sm-pull-11.ant-col-rtl{right:auto;left:45.83333333%}.ant-col-sm-offset-11.ant-col-rtl{margin-right:45.83333333%;margin-left:0}.ant-col-sm-push-12.ant-col-rtl{right:50%;left:auto}.ant-col-sm-pull-12.ant-col-rtl{right:auto;left:50%}.ant-col-sm-offset-12.ant-col-rtl{margin-right:50%;margin-left:0}.ant-col-sm-push-13.ant-col-rtl{right:54.16666667%;left:auto}.ant-col-sm-pull-13.ant-col-rtl{right:auto;left:54.16666667%}.ant-col-sm-offset-13.ant-col-rtl{margin-right:54.16666667%;margin-left:0}.ant-col-sm-push-14.ant-col-rtl{right:58.33333333%;left:auto}.ant-col-sm-pull-14.ant-col-rtl{right:auto;left:58.33333333%}.ant-col-sm-offset-14.ant-col-rtl{margin-right:58.33333333%;margin-left:0}.ant-col-sm-push-15.ant-col-rtl{right:62.5%;left:auto}.ant-col-sm-pull-15.ant-col-rtl{right:auto;left:62.5%}.ant-col-sm-offset-15.ant-col-rtl{margin-right:62.5%;margin-left:0}.ant-col-sm-push-16.ant-col-rtl{right:66.66666667%;left:auto}.ant-col-sm-pull-16.ant-col-rtl{right:auto;left:66.66666667%}.ant-col-sm-offset-16.ant-col-rtl{margin-right:66.66666667%;margin-left:0}.ant-col-sm-push-17.ant-col-rtl{right:70.83333333%;left:auto}.ant-col-sm-pull-17.ant-col-rtl{right:auto;left:70.83333333%}.ant-col-sm-offset-17.ant-col-rtl{margin-right:70.83333333%;margin-left:0}.ant-col-sm-push-18.ant-col-rtl{right:75%;left:auto}.ant-col-sm-pull-18.ant-col-rtl{right:auto;left:75%}.ant-col-sm-offset-18.ant-col-rtl{margin-right:75%;margin-left:0}.ant-col-sm-push-19.ant-col-rtl{right:79.16666667%;left:auto}.ant-col-sm-pull-19.ant-col-rtl{right:auto;left:79.16666667%}.ant-col-sm-offset-19.ant-col-rtl{margin-right:79.16666667%;margin-left:0}.ant-col-sm-push-20.ant-col-rtl{right:83.33333333%;left:auto}.ant-col-sm-pull-20.ant-col-rtl{right:auto;left:83.33333333%}.ant-col-sm-offset-20.ant-col-rtl{margin-right:83.33333333%;margin-left:0}.ant-col-sm-push-21.ant-col-rtl{right:87.5%;left:auto}.ant-col-sm-pull-21.ant-col-rtl{right:auto;left:87.5%}.ant-col-sm-offset-21.ant-col-rtl{margin-right:87.5%;margin-left:0}.ant-col-sm-push-22.ant-col-rtl{right:91.66666667%;left:auto}.ant-col-sm-pull-22.ant-col-rtl{right:auto;left:91.66666667%}.ant-col-sm-offset-22.ant-col-rtl{margin-right:91.66666667%;margin-left:0}.ant-col-sm-push-23.ant-col-rtl{right:95.83333333%;left:auto}.ant-col-sm-pull-23.ant-col-rtl{right:auto;left:95.83333333%}.ant-col-sm-offset-23.ant-col-rtl{margin-right:95.83333333%;margin-left:0}.ant-col-sm-push-24.ant-col-rtl{right:100%;left:auto}.ant-col-sm-pull-24.ant-col-rtl{right:auto;left:100%}.ant-col-sm-offset-24.ant-col-rtl{margin-right:100%;margin-left:0}}@media(min-width: 768px){.ant-col-md-24{display:block;flex:0 0 100%;max-width:100%}.ant-col-md-push-24{left:100%}.ant-col-md-pull-24{right:100%}.ant-col-md-offset-24{margin-left:100%}.ant-col-md-order-24{order:24}.ant-col-md-23{display:block;flex:0 0 95.83333333%;max-width:95.83333333%}.ant-col-md-push-23{left:95.83333333%}.ant-col-md-pull-23{right:95.83333333%}.ant-col-md-offset-23{margin-left:95.83333333%}.ant-col-md-order-23{order:23}.ant-col-md-22{display:block;flex:0 0 91.66666667%;max-width:91.66666667%}.ant-col-md-push-22{left:91.66666667%}.ant-col-md-pull-22{right:91.66666667%}.ant-col-md-offset-22{margin-left:91.66666667%}.ant-col-md-order-22{order:22}.ant-col-md-21{display:block;flex:0 0 87.5%;max-width:87.5%}.ant-col-md-push-21{left:87.5%}.ant-col-md-pull-21{right:87.5%}.ant-col-md-offset-21{margin-left:87.5%}.ant-col-md-order-21{order:21}.ant-col-md-20{display:block;flex:0 0 83.33333333%;max-width:83.33333333%}.ant-col-md-push-20{left:83.33333333%}.ant-col-md-pull-20{right:83.33333333%}.ant-col-md-offset-20{margin-left:83.33333333%}.ant-col-md-order-20{order:20}.ant-col-md-19{display:block;flex:0 0 79.16666667%;max-width:79.16666667%}.ant-col-md-push-19{left:79.16666667%}.ant-col-md-pull-19{right:79.16666667%}.ant-col-md-offset-19{margin-left:79.16666667%}.ant-col-md-order-19{order:19}.ant-col-md-18{display:block;flex:0 0 75%;max-width:75%}.ant-col-md-push-18{left:75%}.ant-col-md-pull-18{right:75%}.ant-col-md-offset-18{margin-left:75%}.ant-col-md-order-18{order:18}.ant-col-md-17{display:block;flex:0 0 70.83333333%;max-width:70.83333333%}.ant-col-md-push-17{left:70.83333333%}.ant-col-md-pull-17{right:70.83333333%}.ant-col-md-offset-17{margin-left:70.83333333%}.ant-col-md-order-17{order:17}.ant-col-md-16{display:block;flex:0 0 66.66666667%;max-width:66.66666667%}.ant-col-md-push-16{left:66.66666667%}.ant-col-md-pull-16{right:66.66666667%}.ant-col-md-offset-16{margin-left:66.66666667%}.ant-col-md-order-16{order:16}.ant-col-md-15{display:block;flex:0 0 62.5%;max-width:62.5%}.ant-col-md-push-15{left:62.5%}.ant-col-md-pull-15{right:62.5%}.ant-col-md-offset-15{margin-left:62.5%}.ant-col-md-order-15{order:15}.ant-col-md-14{display:block;flex:0 0 58.33333333%;max-width:58.33333333%}.ant-col-md-push-14{left:58.33333333%}.ant-col-md-pull-14{right:58.33333333%}.ant-col-md-offset-14{margin-left:58.33333333%}.ant-col-md-order-14{order:14}.ant-col-md-13{display:block;flex:0 0 54.16666667%;max-width:54.16666667%}.ant-col-md-push-13{left:54.16666667%}.ant-col-md-pull-13{right:54.16666667%}.ant-col-md-offset-13{margin-left:54.16666667%}.ant-col-md-order-13{order:13}.ant-col-md-12{display:block;flex:0 0 50%;max-width:50%}.ant-col-md-push-12{left:50%}.ant-col-md-pull-12{right:50%}.ant-col-md-offset-12{margin-left:50%}.ant-col-md-order-12{order:12}.ant-col-md-11{display:block;flex:0 0 45.83333333%;max-width:45.83333333%}.ant-col-md-push-11{left:45.83333333%}.ant-col-md-pull-11{right:45.83333333%}.ant-col-md-offset-11{margin-left:45.83333333%}.ant-col-md-order-11{order:11}.ant-col-md-10{display:block;flex:0 0 41.66666667%;max-width:41.66666667%}.ant-col-md-push-10{left:41.66666667%}.ant-col-md-pull-10{right:41.66666667%}.ant-col-md-offset-10{margin-left:41.66666667%}.ant-col-md-order-10{order:10}.ant-col-md-9{display:block;flex:0 0 37.5%;max-width:37.5%}.ant-col-md-push-9{left:37.5%}.ant-col-md-pull-9{right:37.5%}.ant-col-md-offset-9{margin-left:37.5%}.ant-col-md-order-9{order:9}.ant-col-md-8{display:block;flex:0 0 33.33333333%;max-width:33.33333333%}.ant-col-md-push-8{left:33.33333333%}.ant-col-md-pull-8{right:33.33333333%}.ant-col-md-offset-8{margin-left:33.33333333%}.ant-col-md-order-8{order:8}.ant-col-md-7{display:block;flex:0 0 29.16666667%;max-width:29.16666667%}.ant-col-md-push-7{left:29.16666667%}.ant-col-md-pull-7{right:29.16666667%}.ant-col-md-offset-7{margin-left:29.16666667%}.ant-col-md-order-7{order:7}.ant-col-md-6{display:block;flex:0 0 25%;max-width:25%}.ant-col-md-push-6{left:25%}.ant-col-md-pull-6{right:25%}.ant-col-md-offset-6{margin-left:25%}.ant-col-md-order-6{order:6}.ant-col-md-5{display:block;flex:0 0 20.83333333%;max-width:20.83333333%}.ant-col-md-push-5{left:20.83333333%}.ant-col-md-pull-5{right:20.83333333%}.ant-col-md-offset-5{margin-left:20.83333333%}.ant-col-md-order-5{order:5}.ant-col-md-4{display:block;flex:0 0 16.66666667%;max-width:16.66666667%}.ant-col-md-push-4{left:16.66666667%}.ant-col-md-pull-4{right:16.66666667%}.ant-col-md-offset-4{margin-left:16.66666667%}.ant-col-md-order-4{order:4}.ant-col-md-3{display:block;flex:0 0 12.5%;max-width:12.5%}.ant-col-md-push-3{left:12.5%}.ant-col-md-pull-3{right:12.5%}.ant-col-md-offset-3{margin-left:12.5%}.ant-col-md-order-3{order:3}.ant-col-md-2{display:block;flex:0 0 8.33333333%;max-width:8.33333333%}.ant-col-md-push-2{left:8.33333333%}.ant-col-md-pull-2{right:8.33333333%}.ant-col-md-offset-2{margin-left:8.33333333%}.ant-col-md-order-2{order:2}.ant-col-md-1{display:block;flex:0 0 4.16666667%;max-width:4.16666667%}.ant-col-md-push-1{left:4.16666667%}.ant-col-md-pull-1{right:4.16666667%}.ant-col-md-offset-1{margin-left:4.16666667%}.ant-col-md-order-1{order:1}.ant-col-md-0{display:none}.ant-col-push-0{left:auto}.ant-col-pull-0{right:auto}.ant-col-md-push-0{left:auto}.ant-col-md-pull-0{right:auto}.ant-col-md-offset-0{margin-left:0}.ant-col-md-order-0{order:0}.ant-col-push-0.ant-col-rtl{right:auto}.ant-col-pull-0.ant-col-rtl{left:auto}.ant-col-md-push-0.ant-col-rtl{right:auto}.ant-col-md-pull-0.ant-col-rtl{left:auto}.ant-col-md-offset-0.ant-col-rtl{margin-right:0}.ant-col-md-push-1.ant-col-rtl{right:4.16666667%;left:auto}.ant-col-md-pull-1.ant-col-rtl{right:auto;left:4.16666667%}.ant-col-md-offset-1.ant-col-rtl{margin-right:4.16666667%;margin-left:0}.ant-col-md-push-2.ant-col-rtl{right:8.33333333%;left:auto}.ant-col-md-pull-2.ant-col-rtl{right:auto;left:8.33333333%}.ant-col-md-offset-2.ant-col-rtl{margin-right:8.33333333%;margin-left:0}.ant-col-md-push-3.ant-col-rtl{right:12.5%;left:auto}.ant-col-md-pull-3.ant-col-rtl{right:auto;left:12.5%}.ant-col-md-offset-3.ant-col-rtl{margin-right:12.5%;margin-left:0}.ant-col-md-push-4.ant-col-rtl{right:16.66666667%;left:auto}.ant-col-md-pull-4.ant-col-rtl{right:auto;left:16.66666667%}.ant-col-md-offset-4.ant-col-rtl{margin-right:16.66666667%;margin-left:0}.ant-col-md-push-5.ant-col-rtl{right:20.83333333%;left:auto}.ant-col-md-pull-5.ant-col-rtl{right:auto;left:20.83333333%}.ant-col-md-offset-5.ant-col-rtl{margin-right:20.83333333%;margin-left:0}.ant-col-md-push-6.ant-col-rtl{right:25%;left:auto}.ant-col-md-pull-6.ant-col-rtl{right:auto;left:25%}.ant-col-md-offset-6.ant-col-rtl{margin-right:25%;margin-left:0}.ant-col-md-push-7.ant-col-rtl{right:29.16666667%;left:auto}.ant-col-md-pull-7.ant-col-rtl{right:auto;left:29.16666667%}.ant-col-md-offset-7.ant-col-rtl{margin-right:29.16666667%;margin-left:0}.ant-col-md-push-8.ant-col-rtl{right:33.33333333%;left:auto}.ant-col-md-pull-8.ant-col-rtl{right:auto;left:33.33333333%}.ant-col-md-offset-8.ant-col-rtl{margin-right:33.33333333%;margin-left:0}.ant-col-md-push-9.ant-col-rtl{right:37.5%;left:auto}.ant-col-md-pull-9.ant-col-rtl{right:auto;left:37.5%}.ant-col-md-offset-9.ant-col-rtl{margin-right:37.5%;margin-left:0}.ant-col-md-push-10.ant-col-rtl{right:41.66666667%;left:auto}.ant-col-md-pull-10.ant-col-rtl{right:auto;left:41.66666667%}.ant-col-md-offset-10.ant-col-rtl{margin-right:41.66666667%;margin-left:0}.ant-col-md-push-11.ant-col-rtl{right:45.83333333%;left:auto}.ant-col-md-pull-11.ant-col-rtl{right:auto;left:45.83333333%}.ant-col-md-offset-11.ant-col-rtl{margin-right:45.83333333%;margin-left:0}.ant-col-md-push-12.ant-col-rtl{right:50%;left:auto}.ant-col-md-pull-12.ant-col-rtl{right:auto;left:50%}.ant-col-md-offset-12.ant-col-rtl{margin-right:50%;margin-left:0}.ant-col-md-push-13.ant-col-rtl{right:54.16666667%;left:auto}.ant-col-md-pull-13.ant-col-rtl{right:auto;left:54.16666667%}.ant-col-md-offset-13.ant-col-rtl{margin-right:54.16666667%;margin-left:0}.ant-col-md-push-14.ant-col-rtl{right:58.33333333%;left:auto}.ant-col-md-pull-14.ant-col-rtl{right:auto;left:58.33333333%}.ant-col-md-offset-14.ant-col-rtl{margin-right:58.33333333%;margin-left:0}.ant-col-md-push-15.ant-col-rtl{right:62.5%;left:auto}.ant-col-md-pull-15.ant-col-rtl{right:auto;left:62.5%}.ant-col-md-offset-15.ant-col-rtl{margin-right:62.5%;margin-left:0}.ant-col-md-push-16.ant-col-rtl{right:66.66666667%;left:auto}.ant-col-md-pull-16.ant-col-rtl{right:auto;left:66.66666667%}.ant-col-md-offset-16.ant-col-rtl{margin-right:66.66666667%;margin-left:0}.ant-col-md-push-17.ant-col-rtl{right:70.83333333%;left:auto}.ant-col-md-pull-17.ant-col-rtl{right:auto;left:70.83333333%}.ant-col-md-offset-17.ant-col-rtl{margin-right:70.83333333%;margin-left:0}.ant-col-md-push-18.ant-col-rtl{right:75%;left:auto}.ant-col-md-pull-18.ant-col-rtl{right:auto;left:75%}.ant-col-md-offset-18.ant-col-rtl{margin-right:75%;margin-left:0}.ant-col-md-push-19.ant-col-rtl{right:79.16666667%;left:auto}.ant-col-md-pull-19.ant-col-rtl{right:auto;left:79.16666667%}.ant-col-md-offset-19.ant-col-rtl{margin-right:79.16666667%;margin-left:0}.ant-col-md-push-20.ant-col-rtl{right:83.33333333%;left:auto}.ant-col-md-pull-20.ant-col-rtl{right:auto;left:83.33333333%}.ant-col-md-offset-20.ant-col-rtl{margin-right:83.33333333%;margin-left:0}.ant-col-md-push-21.ant-col-rtl{right:87.5%;left:auto}.ant-col-md-pull-21.ant-col-rtl{right:auto;left:87.5%}.ant-col-md-offset-21.ant-col-rtl{margin-right:87.5%;margin-left:0}.ant-col-md-push-22.ant-col-rtl{right:91.66666667%;left:auto}.ant-col-md-pull-22.ant-col-rtl{right:auto;left:91.66666667%}.ant-col-md-offset-22.ant-col-rtl{margin-right:91.66666667%;margin-left:0}.ant-col-md-push-23.ant-col-rtl{right:95.83333333%;left:auto}.ant-col-md-pull-23.ant-col-rtl{right:auto;left:95.83333333%}.ant-col-md-offset-23.ant-col-rtl{margin-right:95.83333333%;margin-left:0}.ant-col-md-push-24.ant-col-rtl{right:100%;left:auto}.ant-col-md-pull-24.ant-col-rtl{right:auto;left:100%}.ant-col-md-offset-24.ant-col-rtl{margin-right:100%;margin-left:0}}@media(min-width: 992px){.ant-col-lg-24{display:block;flex:0 0 100%;max-width:100%}.ant-col-lg-push-24{left:100%}.ant-col-lg-pull-24{right:100%}.ant-col-lg-offset-24{margin-left:100%}.ant-col-lg-order-24{order:24}.ant-col-lg-23{display:block;flex:0 0 95.83333333%;max-width:95.83333333%}.ant-col-lg-push-23{left:95.83333333%}.ant-col-lg-pull-23{right:95.83333333%}.ant-col-lg-offset-23{margin-left:95.83333333%}.ant-col-lg-order-23{order:23}.ant-col-lg-22{display:block;flex:0 0 91.66666667%;max-width:91.66666667%}.ant-col-lg-push-22{left:91.66666667%}.ant-col-lg-pull-22{right:91.66666667%}.ant-col-lg-offset-22{margin-left:91.66666667%}.ant-col-lg-order-22{order:22}.ant-col-lg-21{display:block;flex:0 0 87.5%;max-width:87.5%}.ant-col-lg-push-21{left:87.5%}.ant-col-lg-pull-21{right:87.5%}.ant-col-lg-offset-21{margin-left:87.5%}.ant-col-lg-order-21{order:21}.ant-col-lg-20{display:block;flex:0 0 83.33333333%;max-width:83.33333333%}.ant-col-lg-push-20{left:83.33333333%}.ant-col-lg-pull-20{right:83.33333333%}.ant-col-lg-offset-20{margin-left:83.33333333%}.ant-col-lg-order-20{order:20}.ant-col-lg-19{display:block;flex:0 0 79.16666667%;max-width:79.16666667%}.ant-col-lg-push-19{left:79.16666667%}.ant-col-lg-pull-19{right:79.16666667%}.ant-col-lg-offset-19{margin-left:79.16666667%}.ant-col-lg-order-19{order:19}.ant-col-lg-18{display:block;flex:0 0 75%;max-width:75%}.ant-col-lg-push-18{left:75%}.ant-col-lg-pull-18{right:75%}.ant-col-lg-offset-18{margin-left:75%}.ant-col-lg-order-18{order:18}.ant-col-lg-17{display:block;flex:0 0 70.83333333%;max-width:70.83333333%}.ant-col-lg-push-17{left:70.83333333%}.ant-col-lg-pull-17{right:70.83333333%}.ant-col-lg-offset-17{margin-left:70.83333333%}.ant-col-lg-order-17{order:17}.ant-col-lg-16{display:block;flex:0 0 66.66666667%;max-width:66.66666667%}.ant-col-lg-push-16{left:66.66666667%}.ant-col-lg-pull-16{right:66.66666667%}.ant-col-lg-offset-16{margin-left:66.66666667%}.ant-col-lg-order-16{order:16}.ant-col-lg-15{display:block;flex:0 0 62.5%;max-width:62.5%}.ant-col-lg-push-15{left:62.5%}.ant-col-lg-pull-15{right:62.5%}.ant-col-lg-offset-15{margin-left:62.5%}.ant-col-lg-order-15{order:15}.ant-col-lg-14{display:block;flex:0 0 58.33333333%;max-width:58.33333333%}.ant-col-lg-push-14{left:58.33333333%}.ant-col-lg-pull-14{right:58.33333333%}.ant-col-lg-offset-14{margin-left:58.33333333%}.ant-col-lg-order-14{order:14}.ant-col-lg-13{display:block;flex:0 0 54.16666667%;max-width:54.16666667%}.ant-col-lg-push-13{left:54.16666667%}.ant-col-lg-pull-13{right:54.16666667%}.ant-col-lg-offset-13{margin-left:54.16666667%}.ant-col-lg-order-13{order:13}.ant-col-lg-12{display:block;flex:0 0 50%;max-width:50%}.ant-col-lg-push-12{left:50%}.ant-col-lg-pull-12{right:50%}.ant-col-lg-offset-12{margin-left:50%}.ant-col-lg-order-12{order:12}.ant-col-lg-11{display:block;flex:0 0 45.83333333%;max-width:45.83333333%}.ant-col-lg-push-11{left:45.83333333%}.ant-col-lg-pull-11{right:45.83333333%}.ant-col-lg-offset-11{margin-left:45.83333333%}.ant-col-lg-order-11{order:11}.ant-col-lg-10{display:block;flex:0 0 41.66666667%;max-width:41.66666667%}.ant-col-lg-push-10{left:41.66666667%}.ant-col-lg-pull-10{right:41.66666667%}.ant-col-lg-offset-10{margin-left:41.66666667%}.ant-col-lg-order-10{order:10}.ant-col-lg-9{display:block;flex:0 0 37.5%;max-width:37.5%}.ant-col-lg-push-9{left:37.5%}.ant-col-lg-pull-9{right:37.5%}.ant-col-lg-offset-9{margin-left:37.5%}.ant-col-lg-order-9{order:9}.ant-col-lg-8{display:block;flex:0 0 33.33333333%;max-width:33.33333333%}.ant-col-lg-push-8{left:33.33333333%}.ant-col-lg-pull-8{right:33.33333333%}.ant-col-lg-offset-8{margin-left:33.33333333%}.ant-col-lg-order-8{order:8}.ant-col-lg-7{display:block;flex:0 0 29.16666667%;max-width:29.16666667%}.ant-col-lg-push-7{left:29.16666667%}.ant-col-lg-pull-7{right:29.16666667%}.ant-col-lg-offset-7{margin-left:29.16666667%}.ant-col-lg-order-7{order:7}.ant-col-lg-6{display:block;flex:0 0 25%;max-width:25%}.ant-col-lg-push-6{left:25%}.ant-col-lg-pull-6{right:25%}.ant-col-lg-offset-6{margin-left:25%}.ant-col-lg-order-6{order:6}.ant-col-lg-5{display:block;flex:0 0 20.83333333%;max-width:20.83333333%}.ant-col-lg-push-5{left:20.83333333%}.ant-col-lg-pull-5{right:20.83333333%}.ant-col-lg-offset-5{margin-left:20.83333333%}.ant-col-lg-order-5{order:5}.ant-col-lg-4{display:block;flex:0 0 16.66666667%;max-width:16.66666667%}.ant-col-lg-push-4{left:16.66666667%}.ant-col-lg-pull-4{right:16.66666667%}.ant-col-lg-offset-4{margin-left:16.66666667%}.ant-col-lg-order-4{order:4}.ant-col-lg-3{display:block;flex:0 0 12.5%;max-width:12.5%}.ant-col-lg-push-3{left:12.5%}.ant-col-lg-pull-3{right:12.5%}.ant-col-lg-offset-3{margin-left:12.5%}.ant-col-lg-order-3{order:3}.ant-col-lg-2{display:block;flex:0 0 8.33333333%;max-width:8.33333333%}.ant-col-lg-push-2{left:8.33333333%}.ant-col-lg-pull-2{right:8.33333333%}.ant-col-lg-offset-2{margin-left:8.33333333%}.ant-col-lg-order-2{order:2}.ant-col-lg-1{display:block;flex:0 0 4.16666667%;max-width:4.16666667%}.ant-col-lg-push-1{left:4.16666667%}.ant-col-lg-pull-1{right:4.16666667%}.ant-col-lg-offset-1{margin-left:4.16666667%}.ant-col-lg-order-1{order:1}.ant-col-lg-0{display:none}.ant-col-push-0{left:auto}.ant-col-pull-0{right:auto}.ant-col-lg-push-0{left:auto}.ant-col-lg-pull-0{right:auto}.ant-col-lg-offset-0{margin-left:0}.ant-col-lg-order-0{order:0}.ant-col-push-0.ant-col-rtl{right:auto}.ant-col-pull-0.ant-col-rtl{left:auto}.ant-col-lg-push-0.ant-col-rtl{right:auto}.ant-col-lg-pull-0.ant-col-rtl{left:auto}.ant-col-lg-offset-0.ant-col-rtl{margin-right:0}.ant-col-lg-push-1.ant-col-rtl{right:4.16666667%;left:auto}.ant-col-lg-pull-1.ant-col-rtl{right:auto;left:4.16666667%}.ant-col-lg-offset-1.ant-col-rtl{margin-right:4.16666667%;margin-left:0}.ant-col-lg-push-2.ant-col-rtl{right:8.33333333%;left:auto}.ant-col-lg-pull-2.ant-col-rtl{right:auto;left:8.33333333%}.ant-col-lg-offset-2.ant-col-rtl{margin-right:8.33333333%;margin-left:0}.ant-col-lg-push-3.ant-col-rtl{right:12.5%;left:auto}.ant-col-lg-pull-3.ant-col-rtl{right:auto;left:12.5%}.ant-col-lg-offset-3.ant-col-rtl{margin-right:12.5%;margin-left:0}.ant-col-lg-push-4.ant-col-rtl{right:16.66666667%;left:auto}.ant-col-lg-pull-4.ant-col-rtl{right:auto;left:16.66666667%}.ant-col-lg-offset-4.ant-col-rtl{margin-right:16.66666667%;margin-left:0}.ant-col-lg-push-5.ant-col-rtl{right:20.83333333%;left:auto}.ant-col-lg-pull-5.ant-col-rtl{right:auto;left:20.83333333%}.ant-col-lg-offset-5.ant-col-rtl{margin-right:20.83333333%;margin-left:0}.ant-col-lg-push-6.ant-col-rtl{right:25%;left:auto}.ant-col-lg-pull-6.ant-col-rtl{right:auto;left:25%}.ant-col-lg-offset-6.ant-col-rtl{margin-right:25%;margin-left:0}.ant-col-lg-push-7.ant-col-rtl{right:29.16666667%;left:auto}.ant-col-lg-pull-7.ant-col-rtl{right:auto;left:29.16666667%}.ant-col-lg-offset-7.ant-col-rtl{margin-right:29.16666667%;margin-left:0}.ant-col-lg-push-8.ant-col-rtl{right:33.33333333%;left:auto}.ant-col-lg-pull-8.ant-col-rtl{right:auto;left:33.33333333%}.ant-col-lg-offset-8.ant-col-rtl{margin-right:33.33333333%;margin-left:0}.ant-col-lg-push-9.ant-col-rtl{right:37.5%;left:auto}.ant-col-lg-pull-9.ant-col-rtl{right:auto;left:37.5%}.ant-col-lg-offset-9.ant-col-rtl{margin-right:37.5%;margin-left:0}.ant-col-lg-push-10.ant-col-rtl{right:41.66666667%;left:auto}.ant-col-lg-pull-10.ant-col-rtl{right:auto;left:41.66666667%}.ant-col-lg-offset-10.ant-col-rtl{margin-right:41.66666667%;margin-left:0}.ant-col-lg-push-11.ant-col-rtl{right:45.83333333%;left:auto}.ant-col-lg-pull-11.ant-col-rtl{right:auto;left:45.83333333%}.ant-col-lg-offset-11.ant-col-rtl{margin-right:45.83333333%;margin-left:0}.ant-col-lg-push-12.ant-col-rtl{right:50%;left:auto}.ant-col-lg-pull-12.ant-col-rtl{right:auto;left:50%}.ant-col-lg-offset-12.ant-col-rtl{margin-right:50%;margin-left:0}.ant-col-lg-push-13.ant-col-rtl{right:54.16666667%;left:auto}.ant-col-lg-pull-13.ant-col-rtl{right:auto;left:54.16666667%}.ant-col-lg-offset-13.ant-col-rtl{margin-right:54.16666667%;margin-left:0}.ant-col-lg-push-14.ant-col-rtl{right:58.33333333%;left:auto}.ant-col-lg-pull-14.ant-col-rtl{right:auto;left:58.33333333%}.ant-col-lg-offset-14.ant-col-rtl{margin-right:58.33333333%;margin-left:0}.ant-col-lg-push-15.ant-col-rtl{right:62.5%;left:auto}.ant-col-lg-pull-15.ant-col-rtl{right:auto;left:62.5%}.ant-col-lg-offset-15.ant-col-rtl{margin-right:62.5%;margin-left:0}.ant-col-lg-push-16.ant-col-rtl{right:66.66666667%;left:auto}.ant-col-lg-pull-16.ant-col-rtl{right:auto;left:66.66666667%}.ant-col-lg-offset-16.ant-col-rtl{margin-right:66.66666667%;margin-left:0}.ant-col-lg-push-17.ant-col-rtl{right:70.83333333%;left:auto}.ant-col-lg-pull-17.ant-col-rtl{right:auto;left:70.83333333%}.ant-col-lg-offset-17.ant-col-rtl{margin-right:70.83333333%;margin-left:0}.ant-col-lg-push-18.ant-col-rtl{right:75%;left:auto}.ant-col-lg-pull-18.ant-col-rtl{right:auto;left:75%}.ant-col-lg-offset-18.ant-col-rtl{margin-right:75%;margin-left:0}.ant-col-lg-push-19.ant-col-rtl{right:79.16666667%;left:auto}.ant-col-lg-pull-19.ant-col-rtl{right:auto;left:79.16666667%}.ant-col-lg-offset-19.ant-col-rtl{margin-right:79.16666667%;margin-left:0}.ant-col-lg-push-20.ant-col-rtl{right:83.33333333%;left:auto}.ant-col-lg-pull-20.ant-col-rtl{right:auto;left:83.33333333%}.ant-col-lg-offset-20.ant-col-rtl{margin-right:83.33333333%;margin-left:0}.ant-col-lg-push-21.ant-col-rtl{right:87.5%;left:auto}.ant-col-lg-pull-21.ant-col-rtl{right:auto;left:87.5%}.ant-col-lg-offset-21.ant-col-rtl{margin-right:87.5%;margin-left:0}.ant-col-lg-push-22.ant-col-rtl{right:91.66666667%;left:auto}.ant-col-lg-pull-22.ant-col-rtl{right:auto;left:91.66666667%}.ant-col-lg-offset-22.ant-col-rtl{margin-right:91.66666667%;margin-left:0}.ant-col-lg-push-23.ant-col-rtl{right:95.83333333%;left:auto}.ant-col-lg-pull-23.ant-col-rtl{right:auto;left:95.83333333%}.ant-col-lg-offset-23.ant-col-rtl{margin-right:95.83333333%;margin-left:0}.ant-col-lg-push-24.ant-col-rtl{right:100%;left:auto}.ant-col-lg-pull-24.ant-col-rtl{right:auto;left:100%}.ant-col-lg-offset-24.ant-col-rtl{margin-right:100%;margin-left:0}}@media(min-width: 1200px){.ant-col-xl-24{display:block;flex:0 0 100%;max-width:100%}.ant-col-xl-push-24{left:100%}.ant-col-xl-pull-24{right:100%}.ant-col-xl-offset-24{margin-left:100%}.ant-col-xl-order-24{order:24}.ant-col-xl-23{display:block;flex:0 0 95.83333333%;max-width:95.83333333%}.ant-col-xl-push-23{left:95.83333333%}.ant-col-xl-pull-23{right:95.83333333%}.ant-col-xl-offset-23{margin-left:95.83333333%}.ant-col-xl-order-23{order:23}.ant-col-xl-22{display:block;flex:0 0 91.66666667%;max-width:91.66666667%}.ant-col-xl-push-22{left:91.66666667%}.ant-col-xl-pull-22{right:91.66666667%}.ant-col-xl-offset-22{margin-left:91.66666667%}.ant-col-xl-order-22{order:22}.ant-col-xl-21{display:block;flex:0 0 87.5%;max-width:87.5%}.ant-col-xl-push-21{left:87.5%}.ant-col-xl-pull-21{right:87.5%}.ant-col-xl-offset-21{margin-left:87.5%}.ant-col-xl-order-21{order:21}.ant-col-xl-20{display:block;flex:0 0 83.33333333%;max-width:83.33333333%}.ant-col-xl-push-20{left:83.33333333%}.ant-col-xl-pull-20{right:83.33333333%}.ant-col-xl-offset-20{margin-left:83.33333333%}.ant-col-xl-order-20{order:20}.ant-col-xl-19{display:block;flex:0 0 79.16666667%;max-width:79.16666667%}.ant-col-xl-push-19{left:79.16666667%}.ant-col-xl-pull-19{right:79.16666667%}.ant-col-xl-offset-19{margin-left:79.16666667%}.ant-col-xl-order-19{order:19}.ant-col-xl-18{display:block;flex:0 0 75%;max-width:75%}.ant-col-xl-push-18{left:75%}.ant-col-xl-pull-18{right:75%}.ant-col-xl-offset-18{margin-left:75%}.ant-col-xl-order-18{order:18}.ant-col-xl-17{display:block;flex:0 0 70.83333333%;max-width:70.83333333%}.ant-col-xl-push-17{left:70.83333333%}.ant-col-xl-pull-17{right:70.83333333%}.ant-col-xl-offset-17{margin-left:70.83333333%}.ant-col-xl-order-17{order:17}.ant-col-xl-16{display:block;flex:0 0 66.66666667%;max-width:66.66666667%}.ant-col-xl-push-16{left:66.66666667%}.ant-col-xl-pull-16{right:66.66666667%}.ant-col-xl-offset-16{margin-left:66.66666667%}.ant-col-xl-order-16{order:16}.ant-col-xl-15{display:block;flex:0 0 62.5%;max-width:62.5%}.ant-col-xl-push-15{left:62.5%}.ant-col-xl-pull-15{right:62.5%}.ant-col-xl-offset-15{margin-left:62.5%}.ant-col-xl-order-15{order:15}.ant-col-xl-14{display:block;flex:0 0 58.33333333%;max-width:58.33333333%}.ant-col-xl-push-14{left:58.33333333%}.ant-col-xl-pull-14{right:58.33333333%}.ant-col-xl-offset-14{margin-left:58.33333333%}.ant-col-xl-order-14{order:14}.ant-col-xl-13{display:block;flex:0 0 54.16666667%;max-width:54.16666667%}.ant-col-xl-push-13{left:54.16666667%}.ant-col-xl-pull-13{right:54.16666667%}.ant-col-xl-offset-13{margin-left:54.16666667%}.ant-col-xl-order-13{order:13}.ant-col-xl-12{display:block;flex:0 0 50%;max-width:50%}.ant-col-xl-push-12{left:50%}.ant-col-xl-pull-12{right:50%}.ant-col-xl-offset-12{margin-left:50%}.ant-col-xl-order-12{order:12}.ant-col-xl-11{display:block;flex:0 0 45.83333333%;max-width:45.83333333%}.ant-col-xl-push-11{left:45.83333333%}.ant-col-xl-pull-11{right:45.83333333%}.ant-col-xl-offset-11{margin-left:45.83333333%}.ant-col-xl-order-11{order:11}.ant-col-xl-10{display:block;flex:0 0 41.66666667%;max-width:41.66666667%}.ant-col-xl-push-10{left:41.66666667%}.ant-col-xl-pull-10{right:41.66666667%}.ant-col-xl-offset-10{margin-left:41.66666667%}.ant-col-xl-order-10{order:10}.ant-col-xl-9{display:block;flex:0 0 37.5%;max-width:37.5%}.ant-col-xl-push-9{left:37.5%}.ant-col-xl-pull-9{right:37.5%}.ant-col-xl-offset-9{margin-left:37.5%}.ant-col-xl-order-9{order:9}.ant-col-xl-8{display:block;flex:0 0 33.33333333%;max-width:33.33333333%}.ant-col-xl-push-8{left:33.33333333%}.ant-col-xl-pull-8{right:33.33333333%}.ant-col-xl-offset-8{margin-left:33.33333333%}.ant-col-xl-order-8{order:8}.ant-col-xl-7{display:block;flex:0 0 29.16666667%;max-width:29.16666667%}.ant-col-xl-push-7{left:29.16666667%}.ant-col-xl-pull-7{right:29.16666667%}.ant-col-xl-offset-7{margin-left:29.16666667%}.ant-col-xl-order-7{order:7}.ant-col-xl-6{display:block;flex:0 0 25%;max-width:25%}.ant-col-xl-push-6{left:25%}.ant-col-xl-pull-6{right:25%}.ant-col-xl-offset-6{margin-left:25%}.ant-col-xl-order-6{order:6}.ant-col-xl-5{display:block;flex:0 0 20.83333333%;max-width:20.83333333%}.ant-col-xl-push-5{left:20.83333333%}.ant-col-xl-pull-5{right:20.83333333%}.ant-col-xl-offset-5{margin-left:20.83333333%}.ant-col-xl-order-5{order:5}.ant-col-xl-4{display:block;flex:0 0 16.66666667%;max-width:16.66666667%}.ant-col-xl-push-4{left:16.66666667%}.ant-col-xl-pull-4{right:16.66666667%}.ant-col-xl-offset-4{margin-left:16.66666667%}.ant-col-xl-order-4{order:4}.ant-col-xl-3{display:block;flex:0 0 12.5%;max-width:12.5%}.ant-col-xl-push-3{left:12.5%}.ant-col-xl-pull-3{right:12.5%}.ant-col-xl-offset-3{margin-left:12.5%}.ant-col-xl-order-3{order:3}.ant-col-xl-2{display:block;flex:0 0 8.33333333%;max-width:8.33333333%}.ant-col-xl-push-2{left:8.33333333%}.ant-col-xl-pull-2{right:8.33333333%}.ant-col-xl-offset-2{margin-left:8.33333333%}.ant-col-xl-order-2{order:2}.ant-col-xl-1{display:block;flex:0 0 4.16666667%;max-width:4.16666667%}.ant-col-xl-push-1{left:4.16666667%}.ant-col-xl-pull-1{right:4.16666667%}.ant-col-xl-offset-1{margin-left:4.16666667%}.ant-col-xl-order-1{order:1}.ant-col-xl-0{display:none}.ant-col-push-0{left:auto}.ant-col-pull-0{right:auto}.ant-col-xl-push-0{left:auto}.ant-col-xl-pull-0{right:auto}.ant-col-xl-offset-0{margin-left:0}.ant-col-xl-order-0{order:0}.ant-col-push-0.ant-col-rtl{right:auto}.ant-col-pull-0.ant-col-rtl{left:auto}.ant-col-xl-push-0.ant-col-rtl{right:auto}.ant-col-xl-pull-0.ant-col-rtl{left:auto}.ant-col-xl-offset-0.ant-col-rtl{margin-right:0}.ant-col-xl-push-1.ant-col-rtl{right:4.16666667%;left:auto}.ant-col-xl-pull-1.ant-col-rtl{right:auto;left:4.16666667%}.ant-col-xl-offset-1.ant-col-rtl{margin-right:4.16666667%;margin-left:0}.ant-col-xl-push-2.ant-col-rtl{right:8.33333333%;left:auto}.ant-col-xl-pull-2.ant-col-rtl{right:auto;left:8.33333333%}.ant-col-xl-offset-2.ant-col-rtl{margin-right:8.33333333%;margin-left:0}.ant-col-xl-push-3.ant-col-rtl{right:12.5%;left:auto}.ant-col-xl-pull-3.ant-col-rtl{right:auto;left:12.5%}.ant-col-xl-offset-3.ant-col-rtl{margin-right:12.5%;margin-left:0}.ant-col-xl-push-4.ant-col-rtl{right:16.66666667%;left:auto}.ant-col-xl-pull-4.ant-col-rtl{right:auto;left:16.66666667%}.ant-col-xl-offset-4.ant-col-rtl{margin-right:16.66666667%;margin-left:0}.ant-col-xl-push-5.ant-col-rtl{right:20.83333333%;left:auto}.ant-col-xl-pull-5.ant-col-rtl{right:auto;left:20.83333333%}.ant-col-xl-offset-5.ant-col-rtl{margin-right:20.83333333%;margin-left:0}.ant-col-xl-push-6.ant-col-rtl{right:25%;left:auto}.ant-col-xl-pull-6.ant-col-rtl{right:auto;left:25%}.ant-col-xl-offset-6.ant-col-rtl{margin-right:25%;margin-left:0}.ant-col-xl-push-7.ant-col-rtl{right:29.16666667%;left:auto}.ant-col-xl-pull-7.ant-col-rtl{right:auto;left:29.16666667%}.ant-col-xl-offset-7.ant-col-rtl{margin-right:29.16666667%;margin-left:0}.ant-col-xl-push-8.ant-col-rtl{right:33.33333333%;left:auto}.ant-col-xl-pull-8.ant-col-rtl{right:auto;left:33.33333333%}.ant-col-xl-offset-8.ant-col-rtl{margin-right:33.33333333%;margin-left:0}.ant-col-xl-push-9.ant-col-rtl{right:37.5%;left:auto}.ant-col-xl-pull-9.ant-col-rtl{right:auto;left:37.5%}.ant-col-xl-offset-9.ant-col-rtl{margin-right:37.5%;margin-left:0}.ant-col-xl-push-10.ant-col-rtl{right:41.66666667%;left:auto}.ant-col-xl-pull-10.ant-col-rtl{right:auto;left:41.66666667%}.ant-col-xl-offset-10.ant-col-rtl{margin-right:41.66666667%;margin-left:0}.ant-col-xl-push-11.ant-col-rtl{right:45.83333333%;left:auto}.ant-col-xl-pull-11.ant-col-rtl{right:auto;left:45.83333333%}.ant-col-xl-offset-11.ant-col-rtl{margin-right:45.83333333%;margin-left:0}.ant-col-xl-push-12.ant-col-rtl{right:50%;left:auto}.ant-col-xl-pull-12.ant-col-rtl{right:auto;left:50%}.ant-col-xl-offset-12.ant-col-rtl{margin-right:50%;margin-left:0}.ant-col-xl-push-13.ant-col-rtl{right:54.16666667%;left:auto}.ant-col-xl-pull-13.ant-col-rtl{right:auto;left:54.16666667%}.ant-col-xl-offset-13.ant-col-rtl{margin-right:54.16666667%;margin-left:0}.ant-col-xl-push-14.ant-col-rtl{right:58.33333333%;left:auto}.ant-col-xl-pull-14.ant-col-rtl{right:auto;left:58.33333333%}.ant-col-xl-offset-14.ant-col-rtl{margin-right:58.33333333%;margin-left:0}.ant-col-xl-push-15.ant-col-rtl{right:62.5%;left:auto}.ant-col-xl-pull-15.ant-col-rtl{right:auto;left:62.5%}.ant-col-xl-offset-15.ant-col-rtl{margin-right:62.5%;margin-left:0}.ant-col-xl-push-16.ant-col-rtl{right:66.66666667%;left:auto}.ant-col-xl-pull-16.ant-col-rtl{right:auto;left:66.66666667%}.ant-col-xl-offset-16.ant-col-rtl{margin-right:66.66666667%;margin-left:0}.ant-col-xl-push-17.ant-col-rtl{right:70.83333333%;left:auto}.ant-col-xl-pull-17.ant-col-rtl{right:auto;left:70.83333333%}.ant-col-xl-offset-17.ant-col-rtl{margin-right:70.83333333%;margin-left:0}.ant-col-xl-push-18.ant-col-rtl{right:75%;left:auto}.ant-col-xl-pull-18.ant-col-rtl{right:auto;left:75%}.ant-col-xl-offset-18.ant-col-rtl{margin-right:75%;margin-left:0}.ant-col-xl-push-19.ant-col-rtl{right:79.16666667%;left:auto}.ant-col-xl-pull-19.ant-col-rtl{right:auto;left:79.16666667%}.ant-col-xl-offset-19.ant-col-rtl{margin-right:79.16666667%;margin-left:0}.ant-col-xl-push-20.ant-col-rtl{right:83.33333333%;left:auto}.ant-col-xl-pull-20.ant-col-rtl{right:auto;left:83.33333333%}.ant-col-xl-offset-20.ant-col-rtl{margin-right:83.33333333%;margin-left:0}.ant-col-xl-push-21.ant-col-rtl{right:87.5%;left:auto}.ant-col-xl-pull-21.ant-col-rtl{right:auto;left:87.5%}.ant-col-xl-offset-21.ant-col-rtl{margin-right:87.5%;margin-left:0}.ant-col-xl-push-22.ant-col-rtl{right:91.66666667%;left:auto}.ant-col-xl-pull-22.ant-col-rtl{right:auto;left:91.66666667%}.ant-col-xl-offset-22.ant-col-rtl{margin-right:91.66666667%;margin-left:0}.ant-col-xl-push-23.ant-col-rtl{right:95.83333333%;left:auto}.ant-col-xl-pull-23.ant-col-rtl{right:auto;left:95.83333333%}.ant-col-xl-offset-23.ant-col-rtl{margin-right:95.83333333%;margin-left:0}.ant-col-xl-push-24.ant-col-rtl{right:100%;left:auto}.ant-col-xl-pull-24.ant-col-rtl{right:auto;left:100%}.ant-col-xl-offset-24.ant-col-rtl{margin-right:100%;margin-left:0}}@media(min-width: 1600px){.ant-col-xxl-24{display:block;flex:0 0 100%;max-width:100%}.ant-col-xxl-push-24{left:100%}.ant-col-xxl-pull-24{right:100%}.ant-col-xxl-offset-24{margin-left:100%}.ant-col-xxl-order-24{order:24}.ant-col-xxl-23{display:block;flex:0 0 95.83333333%;max-width:95.83333333%}.ant-col-xxl-push-23{left:95.83333333%}.ant-col-xxl-pull-23{right:95.83333333%}.ant-col-xxl-offset-23{margin-left:95.83333333%}.ant-col-xxl-order-23{order:23}.ant-col-xxl-22{display:block;flex:0 0 91.66666667%;max-width:91.66666667%}.ant-col-xxl-push-22{left:91.66666667%}.ant-col-xxl-pull-22{right:91.66666667%}.ant-col-xxl-offset-22{margin-left:91.66666667%}.ant-col-xxl-order-22{order:22}.ant-col-xxl-21{display:block;flex:0 0 87.5%;max-width:87.5%}.ant-col-xxl-push-21{left:87.5%}.ant-col-xxl-pull-21{right:87.5%}.ant-col-xxl-offset-21{margin-left:87.5%}.ant-col-xxl-order-21{order:21}.ant-col-xxl-20{display:block;flex:0 0 83.33333333%;max-width:83.33333333%}.ant-col-xxl-push-20{left:83.33333333%}.ant-col-xxl-pull-20{right:83.33333333%}.ant-col-xxl-offset-20{margin-left:83.33333333%}.ant-col-xxl-order-20{order:20}.ant-col-xxl-19{display:block;flex:0 0 79.16666667%;max-width:79.16666667%}.ant-col-xxl-push-19{left:79.16666667%}.ant-col-xxl-pull-19{right:79.16666667%}.ant-col-xxl-offset-19{margin-left:79.16666667%}.ant-col-xxl-order-19{order:19}.ant-col-xxl-18{display:block;flex:0 0 75%;max-width:75%}.ant-col-xxl-push-18{left:75%}.ant-col-xxl-pull-18{right:75%}.ant-col-xxl-offset-18{margin-left:75%}.ant-col-xxl-order-18{order:18}.ant-col-xxl-17{display:block;flex:0 0 70.83333333%;max-width:70.83333333%}.ant-col-xxl-push-17{left:70.83333333%}.ant-col-xxl-pull-17{right:70.83333333%}.ant-col-xxl-offset-17{margin-left:70.83333333%}.ant-col-xxl-order-17{order:17}.ant-col-xxl-16{display:block;flex:0 0 66.66666667%;max-width:66.66666667%}.ant-col-xxl-push-16{left:66.66666667%}.ant-col-xxl-pull-16{right:66.66666667%}.ant-col-xxl-offset-16{margin-left:66.66666667%}.ant-col-xxl-order-16{order:16}.ant-col-xxl-15{display:block;flex:0 0 62.5%;max-width:62.5%}.ant-col-xxl-push-15{left:62.5%}.ant-col-xxl-pull-15{right:62.5%}.ant-col-xxl-offset-15{margin-left:62.5%}.ant-col-xxl-order-15{order:15}.ant-col-xxl-14{display:block;flex:0 0 58.33333333%;max-width:58.33333333%}.ant-col-xxl-push-14{left:58.33333333%}.ant-col-xxl-pull-14{right:58.33333333%}.ant-col-xxl-offset-14{margin-left:58.33333333%}.ant-col-xxl-order-14{order:14}.ant-col-xxl-13{display:block;flex:0 0 54.16666667%;max-width:54.16666667%}.ant-col-xxl-push-13{left:54.16666667%}.ant-col-xxl-pull-13{right:54.16666667%}.ant-col-xxl-offset-13{margin-left:54.16666667%}.ant-col-xxl-order-13{order:13}.ant-col-xxl-12{display:block;flex:0 0 50%;max-width:50%}.ant-col-xxl-push-12{left:50%}.ant-col-xxl-pull-12{right:50%}.ant-col-xxl-offset-12{margin-left:50%}.ant-col-xxl-order-12{order:12}.ant-col-xxl-11{display:block;flex:0 0 45.83333333%;max-width:45.83333333%}.ant-col-xxl-push-11{left:45.83333333%}.ant-col-xxl-pull-11{right:45.83333333%}.ant-col-xxl-offset-11{margin-left:45.83333333%}.ant-col-xxl-order-11{order:11}.ant-col-xxl-10{display:block;flex:0 0 41.66666667%;max-width:41.66666667%}.ant-col-xxl-push-10{left:41.66666667%}.ant-col-xxl-pull-10{right:41.66666667%}.ant-col-xxl-offset-10{margin-left:41.66666667%}.ant-col-xxl-order-10{order:10}.ant-col-xxl-9{display:block;flex:0 0 37.5%;max-width:37.5%}.ant-col-xxl-push-9{left:37.5%}.ant-col-xxl-pull-9{right:37.5%}.ant-col-xxl-offset-9{margin-left:37.5%}.ant-col-xxl-order-9{order:9}.ant-col-xxl-8{display:block;flex:0 0 33.33333333%;max-width:33.33333333%}.ant-col-xxl-push-8{left:33.33333333%}.ant-col-xxl-pull-8{right:33.33333333%}.ant-col-xxl-offset-8{margin-left:33.33333333%}.ant-col-xxl-order-8{order:8}.ant-col-xxl-7{display:block;flex:0 0 29.16666667%;max-width:29.16666667%}.ant-col-xxl-push-7{left:29.16666667%}.ant-col-xxl-pull-7{right:29.16666667%}.ant-col-xxl-offset-7{margin-left:29.16666667%}.ant-col-xxl-order-7{order:7}.ant-col-xxl-6{display:block;flex:0 0 25%;max-width:25%}.ant-col-xxl-push-6{left:25%}.ant-col-xxl-pull-6{right:25%}.ant-col-xxl-offset-6{margin-left:25%}.ant-col-xxl-order-6{order:6}.ant-col-xxl-5{display:block;flex:0 0 20.83333333%;max-width:20.83333333%}.ant-col-xxl-push-5{left:20.83333333%}.ant-col-xxl-pull-5{right:20.83333333%}.ant-col-xxl-offset-5{margin-left:20.83333333%}.ant-col-xxl-order-5{order:5}.ant-col-xxl-4{display:block;flex:0 0 16.66666667%;max-width:16.66666667%}.ant-col-xxl-push-4{left:16.66666667%}.ant-col-xxl-pull-4{right:16.66666667%}.ant-col-xxl-offset-4{margin-left:16.66666667%}.ant-col-xxl-order-4{order:4}.ant-col-xxl-3{display:block;flex:0 0 12.5%;max-width:12.5%}.ant-col-xxl-push-3{left:12.5%}.ant-col-xxl-pull-3{right:12.5%}.ant-col-xxl-offset-3{margin-left:12.5%}.ant-col-xxl-order-3{order:3}.ant-col-xxl-2{display:block;flex:0 0 8.33333333%;max-width:8.33333333%}.ant-col-xxl-push-2{left:8.33333333%}.ant-col-xxl-pull-2{right:8.33333333%}.ant-col-xxl-offset-2{margin-left:8.33333333%}.ant-col-xxl-order-2{order:2}.ant-col-xxl-1{display:block;flex:0 0 4.16666667%;max-width:4.16666667%}.ant-col-xxl-push-1{left:4.16666667%}.ant-col-xxl-pull-1{right:4.16666667%}.ant-col-xxl-offset-1{margin-left:4.16666667%}.ant-col-xxl-order-1{order:1}.ant-col-xxl-0{display:none}.ant-col-push-0{left:auto}.ant-col-pull-0{right:auto}.ant-col-xxl-push-0{left:auto}.ant-col-xxl-pull-0{right:auto}.ant-col-xxl-offset-0{margin-left:0}.ant-col-xxl-order-0{order:0}.ant-col-push-0.ant-col-rtl{right:auto}.ant-col-pull-0.ant-col-rtl{left:auto}.ant-col-xxl-push-0.ant-col-rtl{right:auto}.ant-col-xxl-pull-0.ant-col-rtl{left:auto}.ant-col-xxl-offset-0.ant-col-rtl{margin-right:0}.ant-col-xxl-push-1.ant-col-rtl{right:4.16666667%;left:auto}.ant-col-xxl-pull-1.ant-col-rtl{right:auto;left:4.16666667%}.ant-col-xxl-offset-1.ant-col-rtl{margin-right:4.16666667%;margin-left:0}.ant-col-xxl-push-2.ant-col-rtl{right:8.33333333%;left:auto}.ant-col-xxl-pull-2.ant-col-rtl{right:auto;left:8.33333333%}.ant-col-xxl-offset-2.ant-col-rtl{margin-right:8.33333333%;margin-left:0}.ant-col-xxl-push-3.ant-col-rtl{right:12.5%;left:auto}.ant-col-xxl-pull-3.ant-col-rtl{right:auto;left:12.5%}.ant-col-xxl-offset-3.ant-col-rtl{margin-right:12.5%;margin-left:0}.ant-col-xxl-push-4.ant-col-rtl{right:16.66666667%;left:auto}.ant-col-xxl-pull-4.ant-col-rtl{right:auto;left:16.66666667%}.ant-col-xxl-offset-4.ant-col-rtl{margin-right:16.66666667%;margin-left:0}.ant-col-xxl-push-5.ant-col-rtl{right:20.83333333%;left:auto}.ant-col-xxl-pull-5.ant-col-rtl{right:auto;left:20.83333333%}.ant-col-xxl-offset-5.ant-col-rtl{margin-right:20.83333333%;margin-left:0}.ant-col-xxl-push-6.ant-col-rtl{right:25%;left:auto}.ant-col-xxl-pull-6.ant-col-rtl{right:auto;left:25%}.ant-col-xxl-offset-6.ant-col-rtl{margin-right:25%;margin-left:0}.ant-col-xxl-push-7.ant-col-rtl{right:29.16666667%;left:auto}.ant-col-xxl-pull-7.ant-col-rtl{right:auto;left:29.16666667%}.ant-col-xxl-offset-7.ant-col-rtl{margin-right:29.16666667%;margin-left:0}.ant-col-xxl-push-8.ant-col-rtl{right:33.33333333%;left:auto}.ant-col-xxl-pull-8.ant-col-rtl{right:auto;left:33.33333333%}.ant-col-xxl-offset-8.ant-col-rtl{margin-right:33.33333333%;margin-left:0}.ant-col-xxl-push-9.ant-col-rtl{right:37.5%;left:auto}.ant-col-xxl-pull-9.ant-col-rtl{right:auto;left:37.5%}.ant-col-xxl-offset-9.ant-col-rtl{margin-right:37.5%;margin-left:0}.ant-col-xxl-push-10.ant-col-rtl{right:41.66666667%;left:auto}.ant-col-xxl-pull-10.ant-col-rtl{right:auto;left:41.66666667%}.ant-col-xxl-offset-10.ant-col-rtl{margin-right:41.66666667%;margin-left:0}.ant-col-xxl-push-11.ant-col-rtl{right:45.83333333%;left:auto}.ant-col-xxl-pull-11.ant-col-rtl{right:auto;left:45.83333333%}.ant-col-xxl-offset-11.ant-col-rtl{margin-right:45.83333333%;margin-left:0}.ant-col-xxl-push-12.ant-col-rtl{right:50%;left:auto}.ant-col-xxl-pull-12.ant-col-rtl{right:auto;left:50%}.ant-col-xxl-offset-12.ant-col-rtl{margin-right:50%;margin-left:0}.ant-col-xxl-push-13.ant-col-rtl{right:54.16666667%;left:auto}.ant-col-xxl-pull-13.ant-col-rtl{right:auto;left:54.16666667%}.ant-col-xxl-offset-13.ant-col-rtl{margin-right:54.16666667%;margin-left:0}.ant-col-xxl-push-14.ant-col-rtl{right:58.33333333%;left:auto}.ant-col-xxl-pull-14.ant-col-rtl{right:auto;left:58.33333333%}.ant-col-xxl-offset-14.ant-col-rtl{margin-right:58.33333333%;margin-left:0}.ant-col-xxl-push-15.ant-col-rtl{right:62.5%;left:auto}.ant-col-xxl-pull-15.ant-col-rtl{right:auto;left:62.5%}.ant-col-xxl-offset-15.ant-col-rtl{margin-right:62.5%;margin-left:0}.ant-col-xxl-push-16.ant-col-rtl{right:66.66666667%;left:auto}.ant-col-xxl-pull-16.ant-col-rtl{right:auto;left:66.66666667%}.ant-col-xxl-offset-16.ant-col-rtl{margin-right:66.66666667%;margin-left:0}.ant-col-xxl-push-17.ant-col-rtl{right:70.83333333%;left:auto}.ant-col-xxl-pull-17.ant-col-rtl{right:auto;left:70.83333333%}.ant-col-xxl-offset-17.ant-col-rtl{margin-right:70.83333333%;margin-left:0}.ant-col-xxl-push-18.ant-col-rtl{right:75%;left:auto}.ant-col-xxl-pull-18.ant-col-rtl{right:auto;left:75%}.ant-col-xxl-offset-18.ant-col-rtl{margin-right:75%;margin-left:0}.ant-col-xxl-push-19.ant-col-rtl{right:79.16666667%;left:auto}.ant-col-xxl-pull-19.ant-col-rtl{right:auto;left:79.16666667%}.ant-col-xxl-offset-19.ant-col-rtl{margin-right:79.16666667%;margin-left:0}.ant-col-xxl-push-20.ant-col-rtl{right:83.33333333%;left:auto}.ant-col-xxl-pull-20.ant-col-rtl{right:auto;left:83.33333333%}.ant-col-xxl-offset-20.ant-col-rtl{margin-right:83.33333333%;margin-left:0}.ant-col-xxl-push-21.ant-col-rtl{right:87.5%;left:auto}.ant-col-xxl-pull-21.ant-col-rtl{right:auto;left:87.5%}.ant-col-xxl-offset-21.ant-col-rtl{margin-right:87.5%;margin-left:0}.ant-col-xxl-push-22.ant-col-rtl{right:91.66666667%;left:auto}.ant-col-xxl-pull-22.ant-col-rtl{right:auto;left:91.66666667%}.ant-col-xxl-offset-22.ant-col-rtl{margin-right:91.66666667%;margin-left:0}.ant-col-xxl-push-23.ant-col-rtl{right:95.83333333%;left:auto}.ant-col-xxl-pull-23.ant-col-rtl{right:auto;left:95.83333333%}.ant-col-xxl-offset-23.ant-col-rtl{margin-right:95.83333333%;margin-left:0}.ant-col-xxl-push-24.ant-col-rtl{right:100%;left:auto}.ant-col-xxl-pull-24.ant-col-rtl{right:auto;left:100%}.ant-col-xxl-offset-24.ant-col-rtl{margin-right:100%;margin-left:0}}.ant-row-rtl{direction:rtl}</style><style></style><style>.ant-image{position:relative;display:inline-block}.ant-image-img{width:100%;height:auto;vertical-align:middle}.ant-image-img-placeholder{background-color:#f5f5f5;background-image:url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTYiIGhlaWdodD0iMTYiIHZpZXdCb3g9IjAgMCAxNiAxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48cGF0aCBkPSJNMTQuNSAyLjVoLTEzQS41LjUgMCAwIDAgMSAzdjEwYS41LjUgMCAwIDAgLjUuNWgxM2EuNS41IDAgMCAwIC41LS41VjNhLjUuNSAwIDAgMC0uNS0uNXpNNS4yODEgNC43NWExIDEgMCAwIDEgMCAyIDEgMSAwIDAgMSAwLTJ6bTguMDMgNi44M2EuMTI3LjEyNyAwIDAgMS0uMDgxLjAzSDIuNzY5YS4xMjUuMTI1IDAgMCAxLS4wOTYtLjIwN2wyLjY2MS0zLjE1NmEuMTI2LjEyNiAwIDAgMSAuMTc3LS4wMTZsLjAxNi4wMTZMNy4wOCAxMC4wOWwyLjQ3LTIuOTNhLjEyNi4xMjYgMCAwIDEgLjE3Ny0uMDE2bC4wMTUuMDE2IDMuNTg4IDQuMjQ0YS4xMjcuMTI3IDAgMCAxLS4wMi4xNzV6IiBmaWxsPSIjOEM4QzhDIiBmaWxsLXJ1bGU9Im5vbnplcm8iLz48L3N2Zz4=);background-repeat:no-repeat;background-position:center center;background-size:30%}.ant-image-mask{position:absolute;top:0;right:0;bottom:0;left:0;display:flex;align-items:center;justify-content:center;color:#fff;background:rgba(0,0,0,.5);cursor:pointer;opacity:0;transition:opacity .3s}.ant-image-mask-info{padding:0 4px;overflow:hidden;white-space:nowrap;text-overflow:ellipsis}.ant-image-mask-info .anticon{-webkit-margin-end:4px;margin-inline-end:4px}.ant-image-mask:hover{opacity:1}.ant-image-placeholder{position:absolute;top:0;right:0;bottom:0;left:0}.ant-image-preview{pointer-events:none;height:100%;text-align:center}.ant-image-preview.ant-zoom-enter,.ant-image-preview.ant-zoom-appear{transform:none;opacity:0;animation-duration:.3s;-webkit-user-select:none;-moz-user-select:none;-ms-user-select:none;user-select:none}.ant-image-preview-mask{position:fixed;top:0;right:0;bottom:0;left:0;z-index:1000;height:100%;background-color:rgba(0,0,0,.45)}.ant-image-preview-mask-hidden{display:none}.ant-image-preview-wrap{position:fixed;top:0;right:0;bottom:0;left:0;overflow:auto;outline:0}.ant-image-preview-body{position:absolute;top:0;right:0;bottom:0;left:0;overflow:hidden}.ant-image-preview-img{max-width:100%;max-height:100%;vertical-align:middle;transform:scale3d(1, 1, 1);cursor:grab;transition:transform .3s cubic-bezier(0.215, 0.61, 0.355, 1) 0s;-webkit-user-select:none;-moz-user-select:none;-ms-user-select:none;user-select:none;pointer-events:auto}.ant-image-preview-img-wrapper{position:absolute;top:0;right:0;bottom:0;left:0;transition:transform .3s cubic-bezier(0.215, 0.61, 0.355, 1) 0s}.ant-image-preview-img-wrapper::before{display:inline-block;width:1px;height:50%;margin-right:-1px;content:""}.ant-image-preview-moving .ant-image-preview-img{cursor:grabbing}.ant-image-preview-moving .ant-image-preview-img-wrapper{transition-duration:0s}.ant-image-preview-wrap{z-index:1080}.ant-image-preview-operations-wrapper{position:fixed;top:0;right:0;z-index:1081;width:100%}.ant-image-preview-operations{box-sizing:border-box;margin:0;padding:0;color:rgba(0,0,0,.85);font-size:14px;font-variant:tabular-nums;line-height:1.5715;font-feature-settings:"tnum";display:flex;flex-direction:row-reverse;align-items:center;color:rgba(255,255,255,.85);list-style:none;background:rgba(0,0,0,.1);pointer-events:auto}.ant-image-preview-operations-operation{margin-left:12px;padding:12px;cursor:pointer;transition:all .3s}.ant-image-preview-operations-operation:hover{background:rgba(0,0,0,.2)}.ant-image-preview-operations-operation-disabled{color:rgba(255,255,255,.25);pointer-events:none}.ant-image-preview-operations-operation:last-of-type{margin-left:0}.ant-image-preview-operations-progress{position:absolute;left:50%;transform:translateX(-50%)}.ant-image-preview-operations-icon{font-size:18px}.ant-image-preview-switch-left,.ant-image-preview-switch-right{position:fixed;top:50%;right:8px;z-index:1081;display:flex;align-items:center;justify-content:center;width:44px;height:44px;color:rgba(255,255,255,.85);background:rgba(0,0,0,.1);border-radius:50%;transform:translateY(-50%);cursor:pointer;transition:all .3s;pointer-events:auto}.ant-image-preview-switch-left:hover,.ant-image-preview-switch-right:hover{background:rgba(0,0,0,.2)}.ant-image-preview-switch-left-disabled,.ant-image-preview-switch-right-disabled,.ant-image-preview-switch-left-disabled:hover,.ant-image-preview-switch-right-disabled:hover{color:rgba(255,255,255,.25);background:rgba(0,0,0,.1);cursor:not-allowed}.ant-image-preview-switch-left-disabled>.anticon,.ant-image-preview-switch-right-disabled>.anticon,.ant-image-preview-switch-left-disabled:hover>.anticon,.ant-image-preview-switch-right-disabled:hover>.anticon{cursor:not-allowed}.ant-image-preview-switch-left>.anticon,.ant-image-preview-switch-right>.anticon{font-size:18px}.ant-image-preview-switch-left{left:8px}.ant-image-preview-switch-right{right:8px}</style><style>.ant-list{box-sizing:border-box;margin:0;padding:0;color:rgba(0,0,0,.85);font-size:14px;font-variant:tabular-nums;line-height:1.5715;list-style:none;font-feature-settings:"tnum";position:relative}.ant-list *{outline:none}.ant-list-pagination{margin-top:24px;text-align:right}.ant-list-pagination .ant-pagination-options{text-align:left}.ant-list-more{margin-top:12px;text-align:center}.ant-list-more button{padding-right:32px;padding-left:32px}.ant-list-spin{min-height:40px;text-align:center}.ant-list-empty-text{padding:16px;color:rgba(0,0,0,.25);font-size:14px;text-align:center}.ant-list-items{margin:0;padding:0;list-style:none}.ant-list-item{display:flex;align-items:center;justify-content:space-between;padding:12px 0;color:rgba(0,0,0,.85)}.ant-list-item-meta{display:flex;flex:1;align-items:flex-start;max-width:100%}.ant-list-item-meta-avatar{margin-right:16px}.ant-list-item-meta-content{flex:1 0;width:0;color:rgba(0,0,0,.85)}.ant-list-item-meta-title{margin-bottom:4px;color:rgba(0,0,0,.85);font-size:14px;line-height:1.5715}.ant-list-item-meta-title>a{color:rgba(0,0,0,.85);transition:all .3s}.ant-list-item-meta-title>a:hover{color:#1890ff}.ant-list-item-meta-description{color:rgba(0,0,0,.45);font-size:14px;line-height:1.5715}.ant-list-item-action{flex:0 0 auto;margin-left:48px;padding:0;font-size:0;list-style:none}.ant-list-item-action>li{position:relative;display:inline-block;padding:0 8px;color:rgba(0,0,0,.45);font-size:14px;line-height:1.5715;text-align:center}.ant-list-item-action>li:first-child{padding-left:0}.ant-list-item-action-split{position:absolute;top:50%;right:0;width:1px;height:14px;margin-top:-7px;background-color:#f0f0f0}.ant-list-header{background:rgba(0,0,0,0)}.ant-list-footer{background:rgba(0,0,0,0)}.ant-list-header,.ant-list-footer{padding-top:12px;padding-bottom:12px}.ant-list-empty{padding:16px 0;color:rgba(0,0,0,.45);font-size:12px;text-align:center}.ant-list-split .ant-list-item{border-bottom:1px solid #f0f0f0}.ant-list-split .ant-list-item:last-child{border-bottom:none}.ant-list-split .ant-list-header{border-bottom:1px solid #f0f0f0}.ant-list-split.ant-list-empty .ant-list-footer{border-top:1px solid #f0f0f0}.ant-list-loading .ant-list-spin-nested-loading{min-height:32px}.ant-list-split.ant-list-something-after-last-item .ant-spin-container>.ant-list-items>.ant-list-item:last-child{border-bottom:1px solid #f0f0f0}.ant-list-lg .ant-list-item{padding:16px 24px}.ant-list-sm .ant-list-item{padding:8px 16px}.ant-list-vertical .ant-list-item{align-items:initial}.ant-list-vertical .ant-list-item-main{display:block;flex:1}.ant-list-vertical .ant-list-item-extra{margin-left:40px}.ant-list-vertical .ant-list-item-meta{margin-bottom:16px}.ant-list-vertical .ant-list-item-meta-title{margin-bottom:12px;color:rgba(0,0,0,.85);font-size:16px;line-height:24px}.ant-list-vertical .ant-list-item-action{margin-top:16px;margin-left:auto}.ant-list-vertical .ant-list-item-action>li{padding:0 16px}.ant-list-vertical .ant-list-item-action>li:first-child{padding-left:0}.ant-list-grid .ant-col>.ant-list-item{display:block;max-width:100%;margin-bottom:16px;padding-top:0;padding-bottom:0;border-bottom:none}.ant-list-item-no-flex{display:block}.ant-list:not(.ant-list-vertical) .ant-list-item-no-flex .ant-list-item-action{float:right}.ant-list-bordered{border:1px solid #d9d9d9;border-radius:2px}.ant-list-bordered .ant-list-header{padding-right:24px;padding-left:24px}.ant-list-bordered .ant-list-footer{padding-right:24px;padding-left:24px}.ant-list-bordered .ant-list-item{padding-right:24px;padding-left:24px}.ant-list-bordered .ant-list-pagination{margin:16px 24px}.ant-list-bordered.ant-list-sm .ant-list-item{padding:8px 16px}.ant-list-bordered.ant-list-sm .ant-list-header,.ant-list-bordered.ant-list-sm .ant-list-footer{padding:8px 16px}.ant-list-bordered.ant-list-lg .ant-list-item{padding:16px 24px}.ant-list-bordered.ant-list-lg .ant-list-header,.ant-list-bordered.ant-list-lg .ant-list-footer{padding:16px 24px}@media screen and (max-width: 768px){.ant-list-item-action{margin-left:24px}.ant-list-vertical .ant-list-item-extra{margin-left:24px}}@media screen and (max-width: 576px){.ant-list-item{flex-wrap:wrap}.ant-list-item-action{margin-left:12px}.ant-list-vertical .ant-list-item{flex-wrap:wrap-reverse}.ant-list-vertical .ant-list-item-main{min-width:220px}.ant-list-vertical .ant-list-item-extra{margin:auto auto 16px}}.ant-list-rtl{direction:rtl;text-align:right}.ant-list-rtl .ReactVirtualized__List .ant-list-item{direction:rtl}.ant-list-rtl .ant-list-pagination{text-align:left}.ant-list-rtl .ant-list-item-meta-avatar{margin-right:0;margin-left:16px}.ant-list-rtl .ant-list-item-action{margin-right:48px;margin-left:0}.ant-list.ant-list-rtl .ant-list-item-action>li:first-child{padding-right:0;padding-left:16px}.ant-list-rtl .ant-list-item-action-split{right:auto;left:0}.ant-list-rtl.ant-list-vertical .ant-list-item-extra{margin-right:40px;margin-left:0}.ant-list-rtl.ant-list-vertical .ant-list-item-action{margin-right:auto}.ant-list-rtl .ant-list-vertical .ant-list-item-action>li:first-child{padding-right:0;padding-left:16px}.ant-list-rtl .ant-list:not(.ant-list-vertical) .ant-list-item-no-flex .ant-list-item-action{float:left}@media screen and (max-width: 768px){.ant-list-rtl .ant-list-item-action{margin-right:24px;margin-left:0}.ant-list-rtl .ant-list-vertical .ant-list-item-extra{margin-right:24px;margin-left:0}}@media screen and (max-width: 576px){.ant-list-rtl .ant-list-item-action{margin-right:22px;margin-left:0}.ant-list-rtl.ant-list-vertical .ant-list-item-extra{margin:auto auto 16px}}</style><style>.ant-message{box-sizing:border-box;margin:0;padding:0;color:rgba(0,0,0,.85);font-size:14px;font-variant:tabular-nums;line-height:1.5715;list-style:none;font-feature-settings:"tnum";position:fixed;top:8px;left:0;z-index:1010;width:100%;pointer-events:none}.ant-message-notice{padding:8px;text-align:center}.ant-message-notice-content{display:inline-block;padding:10px 16px;background:#fff;border-radius:2px;box-shadow:0 3px 6px -4px rgba(0,0,0,.12),0 6px 16px 0 rgba(0,0,0,.08),0 9px 28px 8px rgba(0,0,0,.05);pointer-events:all}.ant-message-success .anticon{color:#52c41a}.ant-message-error .anticon{color:#ff4d4f}.ant-message-warning .anticon{color:#faad14}.ant-message-info .anticon,.ant-message-loading .anticon{color:#1890ff}.ant-message .anticon{position:relative;top:1px;margin-right:8px;font-size:16px}.ant-message-notice.ant-move-up-leave.ant-move-up-leave-active{animation-name:MessageMoveOut;animation-duration:.3s}@keyframes MessageMoveOut{0%{max-height:150px;padding:8px;opacity:1}100%{max-height:0;padding:0;opacity:0}}.ant-message-rtl{direction:rtl}.ant-message-rtl span{direction:rtl}.ant-message-rtl .anticon{margin-right:0;margin-left:8px}</style><style>.ant-progress{box-sizing:border-box;margin:0;padding:0;color:rgba(0,0,0,.85);font-size:14px;font-variant:tabular-nums;line-height:1.5715;list-style:none;font-feature-settings:"tnum";display:inline-block}.ant-progress-line{position:relative;width:100%;font-size:14px}.ant-progress-steps{display:inline-block}.ant-progress-steps-outer{display:flex;flex-direction:row;align-items:center}.ant-progress-steps-item{flex-shrink:0;min-width:2px;margin-right:2px;background:#f3f3f3;transition:all .3s}.ant-progress-steps-item-active{background:#1890ff}.ant-progress-small.ant-progress-line,.ant-progress-small.ant-progress-line .ant-progress-text .anticon{font-size:12px}.ant-progress-outer{display:inline-block;width:100%;margin-right:0;padding-right:0}.ant-progress-show-info .ant-progress-outer{margin-right:calc(-2em - 8px);padding-right:calc(2em + 8px)}.ant-progress-inner{position:relative;display:inline-block;width:100%;overflow:hidden;vertical-align:middle;background-color:#f5f5f5;border-radius:100px}.ant-progress-circle-trail{stroke:#f5f5f5}.ant-progress-circle-path{animation:ant-progress-appear .3s}.ant-progress-inner:not(.ant-progress-circle-gradient) .ant-progress-circle-path{stroke:#1890ff}.ant-progress-success-bg,.ant-progress-bg{position:relative;background-color:#1890ff;border-radius:100px;transition:all .4s cubic-bezier(0.08, 0.82, 0.17, 1) 0s}.ant-progress-success-bg{position:absolute;top:0;left:0;background-color:#52c41a}.ant-progress-text{display:inline-block;width:2em;margin-left:8px;color:rgba(0,0,0,.85);font-size:1em;line-height:1;white-space:nowrap;text-align:left;vertical-align:middle;word-break:normal}.ant-progress-text .anticon{font-size:14px}.ant-progress-status-active .ant-progress-bg::before{position:absolute;top:0;right:0;bottom:0;left:0;background:#fff;border-radius:10px;opacity:0;animation:ant-progress-active 2.4s cubic-bezier(0.23, 1, 0.32, 1) infinite;content:""}.ant-progress-status-exception .ant-progress-bg{background-color:#ff4d4f}.ant-progress-status-exception .ant-progress-text{color:#ff4d4f}.ant-progress-status-exception .ant-progress-inner:not(.ant-progress-circle-gradient) .ant-progress-circle-path{stroke:#ff4d4f}.ant-progress-status-success .ant-progress-bg{background-color:#52c41a}.ant-progress-status-success .ant-progress-text{color:#52c41a}.ant-progress-status-success .ant-progress-inner:not(.ant-progress-circle-gradient) .ant-progress-circle-path{stroke:#52c41a}.ant-progress-circle .ant-progress-inner{position:relative;line-height:1;background-color:rgba(0,0,0,0)}.ant-progress-circle .ant-progress-text{position:absolute;top:50%;left:50%;width:100%;margin:0;padding:0;color:rgba(0,0,0,.85);font-size:1em;line-height:1;white-space:normal;text-align:center;transform:translate(-50%, -50%)}.ant-progress-circle .ant-progress-text .anticon{font-size:1.16666667em}.ant-progress-circle.ant-progress-status-exception .ant-progress-text{color:#ff4d4f}.ant-progress-circle.ant-progress-status-success .ant-progress-text{color:#52c41a}@keyframes ant-progress-active{0%{transform:translateX(-100%) scaleX(0);opacity:.1}20%{transform:translateX(-100%) scaleX(0);opacity:.5}100%{transform:translateX(0) scaleX(1);opacity:0}}.ant-progress-rtl{direction:rtl}.ant-progress-rtl.ant-progress-show-info .ant-progress-outer{margin-right:0;margin-left:calc(-2em - 8px);padding-right:0;padding-left:calc(2em + 8px)}.ant-progress-rtl .ant-progress-success-bg{right:0;left:auto}.ant-progress-rtl.ant-progress-line .ant-progress-text,.ant-progress-rtl.ant-progress-steps .ant-progress-text{margin-right:8px;margin-left:0;text-align:right}</style><style>.ant-spin{box-sizing:border-box;margin:0;padding:0;color:rgba(0,0,0,.85);font-size:14px;font-variant:tabular-nums;line-height:1.5715;list-style:none;font-feature-settings:"tnum";position:absolute;display:none;color:#1890ff;text-align:center;vertical-align:middle;opacity:0;transition:transform .3s cubic-bezier(0.78, 0.14, 0.15, 0.86)}.ant-spin-spinning{position:static;display:inline-block;opacity:1}.ant-spin-nested-loading{position:relative}.ant-spin-nested-loading>div>.ant-spin{position:absolute;top:0;left:0;z-index:4;display:block;width:100%;height:100%;max-height:400px}.ant-spin-nested-loading>div>.ant-spin .ant-spin-dot{position:absolute;top:50%;left:50%;margin:-10px}.ant-spin-nested-loading>div>.ant-spin .ant-spin-text{position:absolute;top:50%;width:100%;padding-top:5px;text-shadow:0 1px 2px #fff}.ant-spin-nested-loading>div>.ant-spin.ant-spin-show-text .ant-spin-dot{margin-top:-20px}.ant-spin-nested-loading>div>.ant-spin-sm .ant-spin-dot{margin:-7px}.ant-spin-nested-loading>div>.ant-spin-sm .ant-spin-text{padding-top:2px}.ant-spin-nested-loading>div>.ant-spin-sm.ant-spin-show-text .ant-spin-dot{margin-top:-17px}.ant-spin-nested-loading>div>.ant-spin-lg .ant-spin-dot{margin:-16px}.ant-spin-nested-loading>div>.ant-spin-lg .ant-spin-text{padding-top:11px}.ant-spin-nested-loading>div>.ant-spin-lg.ant-spin-show-text .ant-spin-dot{margin-top:-26px}.ant-spin-container{position:relative;transition:opacity .3s}.ant-spin-container::after{position:absolute;top:0;right:0;bottom:0;left:0;z-index:10;display:none \9 ;width:100%;height:100%;background:#fff;opacity:0;transition:all .3s;content:"";pointer-events:none}.ant-spin-blur{clear:both;opacity:.5;-webkit-user-select:none;-moz-user-select:none;-ms-user-select:none;user-select:none;pointer-events:none}.ant-spin-blur::after{opacity:.4;pointer-events:auto}.ant-spin-tip{color:rgba(0,0,0,.45)}.ant-spin-dot{position:relative;display:inline-block;font-size:20px;width:1em;height:1em}.ant-spin-dot-item{position:absolute;display:block;width:9px;height:9px;background-color:#1890ff;border-radius:100%;transform:scale(0.75);transform-origin:50% 50%;opacity:.3;animation:antSpinMove 1s infinite linear alternate}.ant-spin-dot-item:nth-child(1){top:0;left:0}.ant-spin-dot-item:nth-child(2){top:0;right:0;animation-delay:.4s}.ant-spin-dot-item:nth-child(3){right:0;bottom:0;animation-delay:.8s}.ant-spin-dot-item:nth-child(4){bottom:0;left:0;animation-delay:1.2s}.ant-spin-dot-spin{transform:rotate(0deg);animation:antRotate 1.2s infinite linear}.ant-spin-sm .ant-spin-dot{font-size:14px}.ant-spin-sm .ant-spin-dot i{width:6px;height:6px}.ant-spin-lg .ant-spin-dot{font-size:32px}.ant-spin-lg .ant-spin-dot i{width:14px;height:14px}.ant-spin.ant-spin-show-text .ant-spin-text{display:block}@media all and (-ms-high-contrast: none),(-ms-high-contrast: active){.ant-spin-blur{background:#fff;opacity:.5}}@keyframes antSpinMove{to{opacity:1}}@keyframes antRotate{to{transform:rotate(360deg)}}.ant-spin-rtl{direction:rtl}.ant-spin-rtl .ant-spin-dot-spin{transform:rotate(-45deg);animation-name:antRotateRtl}@keyframes antRotateRtl{to{transform:rotate(-405deg)}}</style><style>.ant-tooltip{box-sizing:border-box;margin:0;padding:0;color:rgba(0,0,0,.85);font-size:14px;font-variant:tabular-nums;line-height:1.5715;list-style:none;font-feature-settings:"tnum";position:absolute;z-index:1070;display:block;width:-moz-max-content;width:max-content;width:intrinsic;max-width:250px;visibility:visible}.ant-tooltip-content{position:relative}.ant-tooltip-hidden{display:none}.ant-tooltip-placement-top,.ant-tooltip-placement-topLeft,.ant-tooltip-placement-topRight{padding-bottom:14.3137085px}.ant-tooltip-placement-right,.ant-tooltip-placement-rightTop,.ant-tooltip-placement-rightBottom{padding-left:14.3137085px}.ant-tooltip-placement-bottom,.ant-tooltip-placement-bottomLeft,.ant-tooltip-placement-bottomRight{padding-top:14.3137085px}.ant-tooltip-placement-left,.ant-tooltip-placement-leftTop,.ant-tooltip-placement-leftBottom{padding-right:14.3137085px}.ant-tooltip-inner{min-width:30px;min-height:32px;padding:6px 8px;color:#fff;text-align:left;text-decoration:none;word-wrap:break-word;background-color:rgba(0,0,0,.75);border-radius:2px;box-shadow:0 3px 6px -4px rgba(0,0,0,.12),0 6px 16px 0 rgba(0,0,0,.08),0 9px 28px 8px rgba(0,0,0,.05)}.ant-tooltip-arrow{position:absolute;z-index:2;display:block;width:22px;height:22px;overflow:hidden;background:rgba(0,0,0,0);pointer-events:none}.ant-tooltip-arrow-content{--antd-arrow-background-color: linear-gradient(to right bottom, rgba(0, 0, 0, 0.65), rgba(0, 0, 0, 0.75));position:absolute;top:0;right:0;bottom:0;left:0;display:block;width:11.3137085px;height:11.3137085px;margin:auto;content:"";pointer-events:auto;border-radius:0 0 2px;pointer-events:none}.ant-tooltip-arrow-content::before{position:absolute;top:-11.3137085px;left:-11.3137085px;width:33.9411255px;height:33.9411255px;background:var(--antd-arrow-background-color);background-repeat:no-repeat;background-position:-10px -10px;content:"";-webkit-clip-path:inset(33% 33%);clip-path:inset(33% 33%);-webkit-clip-path:path("M 9.849242404917499 24.091883092036785 A 5 5 0 0 1 13.384776310850237 22.627416997969522 L 20.627416997969522 22.627416997969522 A 2 2 0 0 0 22.627416997969522 20.627416997969522 L 22.627416997969522 13.384776310850237 A 5 5 0 0 1 24.091883092036785 9.849242404917499 L 23.091883092036785 9.849242404917499 L 9.849242404917499 23.091883092036785 Z");clip-path:path("M 9.849242404917499 24.091883092036785 A 5 5 0 0 1 13.384776310850237 22.627416997969522 L 20.627416997969522 22.627416997969522 A 2 2 0 0 0 22.627416997969522 20.627416997969522 L 22.627416997969522 13.384776310850237 A 5 5 0 0 1 24.091883092036785 9.849242404917499 L 23.091883092036785 9.849242404917499 L 9.849242404917499 23.091883092036785 Z")}.ant-tooltip-placement-top .ant-tooltip-arrow,.ant-tooltip-placement-topLeft .ant-tooltip-arrow,.ant-tooltip-placement-topRight .ant-tooltip-arrow{bottom:0;transform:translateY(100%)}.ant-tooltip-placement-top .ant-tooltip-arrow-content,.ant-tooltip-placement-topLeft .ant-tooltip-arrow-content,.ant-tooltip-placement-topRight .ant-tooltip-arrow-content{box-shadow:3px 3px 7px rgba(0,0,0,.07);transform:translateY(-11px) rotate(45deg)}.ant-tooltip-placement-top .ant-tooltip-arrow{left:50%;transform:translateY(100%) translateX(-50%)}.ant-tooltip-placement-topLeft .ant-tooltip-arrow{left:13px}.ant-tooltip-placement-topRight .ant-tooltip-arrow{right:13px}.ant-tooltip-placement-right .ant-tooltip-arrow,.ant-tooltip-placement-rightTop .ant-tooltip-arrow,.ant-tooltip-placement-rightBottom .ant-tooltip-arrow{left:0;transform:translateX(-100%)}.ant-tooltip-placement-right .ant-tooltip-arrow-content,.ant-tooltip-placement-rightTop .ant-tooltip-arrow-content,.ant-tooltip-placement-rightBottom .ant-tooltip-arrow-content{box-shadow:-3px 3px 7px rgba(0,0,0,.07);transform:translateX(11px) rotate(135deg)}.ant-tooltip-placement-right .ant-tooltip-arrow{top:50%;transform:translateX(-100%) translateY(-50%)}.ant-tooltip-placement-rightTop .ant-tooltip-arrow{top:5px}.ant-tooltip-placement-rightBottom .ant-tooltip-arrow{bottom:5px}.ant-tooltip-placement-left .ant-tooltip-arrow,.ant-tooltip-placement-leftTop .ant-tooltip-arrow,.ant-tooltip-placement-leftBottom .ant-tooltip-arrow{right:0;transform:translateX(100%)}.ant-tooltip-placement-left .ant-tooltip-arrow-content,.ant-tooltip-placement-leftTop .ant-tooltip-arrow-content,.ant-tooltip-placement-leftBottom .ant-tooltip-arrow-content{box-shadow:3px -3px 7px rgba(0,0,0,.07);transform:translateX(-11px) rotate(315deg)}.ant-tooltip-placement-left .ant-tooltip-arrow{top:50%;transform:translateX(100%) translateY(-50%)}.ant-tooltip-placement-leftTop .ant-tooltip-arrow{top:5px}.ant-tooltip-placement-leftBottom .ant-tooltip-arrow{bottom:5px}.ant-tooltip-placement-bottom .ant-tooltip-arrow,.ant-tooltip-placement-bottomLeft .ant-tooltip-arrow,.ant-tooltip-placement-bottomRight .ant-tooltip-arrow{top:0;transform:translateY(-100%)}.ant-tooltip-placement-bottom .ant-tooltip-arrow-content,.ant-tooltip-placement-bottomLeft .ant-tooltip-arrow-content,.ant-tooltip-placement-bottomRight .ant-tooltip-arrow-content{box-shadow:-3px -3px 7px rgba(0,0,0,.07);transform:translateY(11px) rotate(225deg)}.ant-tooltip-placement-bottom .ant-tooltip-arrow{left:50%;transform:translateY(-100%) translateX(-50%)}.ant-tooltip-placement-bottomLeft .ant-tooltip-arrow{left:13px}.ant-tooltip-placement-bottomRight .ant-tooltip-arrow{right:13px}.ant-tooltip-pink .ant-tooltip-inner{background-color:#eb2f96}.ant-tooltip-pink .ant-tooltip-arrow-content::before{background:#eb2f96}.ant-tooltip-magenta .ant-tooltip-inner{background-color:#eb2f96}.ant-tooltip-magenta .ant-tooltip-arrow-content::before{background:#eb2f96}.ant-tooltip-red .ant-tooltip-inner{background-color:#f5222d}.ant-tooltip-red .ant-tooltip-arrow-content::before{background:#f5222d}.ant-tooltip-volcano .ant-tooltip-inner{background-color:#fa541c}.ant-tooltip-volcano .ant-tooltip-arrow-content::before{background:#fa541c}.ant-tooltip-orange .ant-tooltip-inner{background-color:#fa8c16}.ant-tooltip-orange .ant-tooltip-arrow-content::before{background:#fa8c16}.ant-tooltip-yellow .ant-tooltip-inner{background-color:#fadb14}.ant-tooltip-yellow .ant-tooltip-arrow-content::before{background:#fadb14}.ant-tooltip-gold .ant-tooltip-inner{background-color:#faad14}.ant-tooltip-gold .ant-tooltip-arrow-content::before{background:#faad14}.ant-tooltip-cyan .ant-tooltip-inner{background-color:#13c2c2}.ant-tooltip-cyan .ant-tooltip-arrow-content::before{background:#13c2c2}.ant-tooltip-lime .ant-tooltip-inner{background-color:#a0d911}.ant-tooltip-lime .ant-tooltip-arrow-content::before{background:#a0d911}.ant-tooltip-green .ant-tooltip-inner{background-color:#52c41a}.ant-tooltip-green .ant-tooltip-arrow-content::before{background:#52c41a}.ant-tooltip-blue .ant-tooltip-inner{background-color:#1890ff}.ant-tooltip-blue .ant-tooltip-arrow-content::before{background:#1890ff}.ant-tooltip-geekblue .ant-tooltip-inner{background-color:#2f54eb}.ant-tooltip-geekblue .ant-tooltip-arrow-content::before{background:#2f54eb}.ant-tooltip-purple .ant-tooltip-inner{background-color:#722ed1}.ant-tooltip-purple .ant-tooltip-arrow-content::before{background:#722ed1}.ant-tooltip-rtl{direction:rtl}.ant-tooltip-rtl .ant-tooltip-inner{text-align:right}</style><style>.introjs-overlay{position:absolute;box-sizing:content-box;z-index:999999;opacity:0;transition:all .3s ease-out}.introjs-showElement{z-index:9999999 !important}tr.introjs-showElement>td{z-index:9999999 !important;position:relative}tr.introjs-showElement>th{z-index:9999999 !important;position:relative}.introjs-disableInteraction{z-index:99999999 !important;position:absolute;background-color:#fff;opacity:0}.introjs-relativePosition{position:relative}.introjs-helperLayer{box-sizing:content-box;position:absolute;z-index:9999998;border-radius:4px;transition:all .3s ease-out}.introjs-helperLayer *{box-sizing:content-box}.introjs-helperLayer :before{box-sizing:content-box}.introjs-helperLayer :after{box-sizing:content-box}.introjs-tooltipReferenceLayer{font-family:"Helvetica Neue",Inter,ui-sans-serif,"Apple Color Emoji",Helvetica,Arial,sans-serif;box-sizing:content-box;position:absolute;visibility:hidden;z-index:100000000;background-color:rgba(0,0,0,0);transition:all .3s ease-out}.introjs-tooltipReferenceLayer *{font-family:"Helvetica Neue",Inter,ui-sans-serif,"Apple Color Emoji",Helvetica,Arial,sans-serif}.introjs-helperNumberLayer{font-family:"Helvetica Neue",Inter,ui-sans-serif,"Apple Color Emoji",Helvetica,Arial,sans-serif;color:#9e9e9e;text-align:center;padding-top:10px;padding-bottom:10px}.introjs-arrow{border:5px solid rgba(0,0,0,0);content:"";position:absolute}.introjs-arrow.top{top:-10px;left:10px;border-bottom-color:#fff}.introjs-arrow.top-right{top:-10px;right:10px;border-bottom-color:#fff}.introjs-arrow.top-middle{top:-10px;left:50%;margin-left:-5px;border-bottom-color:#fff}.introjs-arrow.right{right:-10px;top:10px;border-left-color:#fff}.introjs-arrow.right-bottom{bottom:10px;right:-10px;border-left-color:#fff}.introjs-arrow.bottom{bottom:-10px;left:10px;border-top-color:#fff}.introjs-arrow.bottom-right{bottom:-10px;right:10px;border-top-color:#fff}.introjs-arrow.bottom-middle{bottom:-10px;left:50%;margin-left:-5px;border-top-color:#fff}.introjs-arrow.left{left:-10px;top:10px;border-right-color:#fff}.introjs-arrow.left-bottom{left:-10px;bottom:10px;border-right-color:#fff}.introjs-tooltip{box-sizing:content-box;position:absolute;visibility:visible;background-color:#fff;min-width:250px;max-width:300px;border-radius:5px;box-shadow:0 3px 30px rgba(33,33,33,.3);transition:opacity .1s ease-out}.introjs-tooltiptext{padding:20px}.introjs-dontShowAgain{padding-left:20px;padding-right:20px}.introjs-dontShowAgain input{padding:0;margin:0;margin-bottom:2px;display:inline;width:10px;height:10px}.introjs-dontShowAgain label{font-size:14px;display:inline-block;font-weight:400;margin:0 0 0 5px;padding:0;background-color:#fff;color:#616161;-webkit-user-select:none;user-select:none}.introjs-tooltip-title{font-size:18px;width:90%;min-height:1.5em;margin:0;padding:0;font-weight:700;line-height:1.5}.introjs-tooltip-header{position:relative;padding-left:20px;padding-right:20px;padding-top:10px;min-height:1.5em}.introjs-tooltipbuttons{border-top:1px solid #e0e0e0;padding:10px;text-align:right;white-space:nowrap}.introjs-tooltipbuttons:after{content:"";visibility:hidden;display:block;height:0;clear:both}.introjs-button{box-sizing:content-box;position:relative;overflow:visible;padding:.5rem 1rem;border:1px solid #bdbdbd;text-decoration:none;text-shadow:1px 1px 0 #fff;font-size:14px;color:#424242;white-space:nowrap;cursor:pointer;outline:0;background-color:#f4f4f4;border-radius:.2em;zoom:1;display:inline}.introjs-button:hover{outline:0;text-decoration:none;border-color:#9e9e9e;background-color:#e0e0e0;color:#212121}.introjs-button:focus{outline:0;text-decoration:none;background-color:#eee;box-shadow:0 0 0 .2rem rgba(158,158,158,.5);border:1px solid #616161;color:#212121}.introjs-button:active{outline:0;text-decoration:none;background-color:#e0e0e0;border-color:#9e9e9e;color:#212121}.introjs-button::-moz-focus-inner{padding:0;border:0}.introjs-skipbutton{position:absolute;top:0;right:0;display:inline-block;width:45px;height:45px;line-height:45px;color:#616161;font-size:22px;cursor:pointer;font-weight:700;text-align:center;text-decoration:none}.introjs-skipbutton:focus,.introjs-skipbutton:hover{color:#212121;outline:0;text-decoration:none}.introjs-prevbutton{float:left}.introjs-nextbutton{float:right}.introjs-disabled{color:#9e9e9e;border-color:#bdbdbd;box-shadow:none;cursor:default;background-color:#f4f4f4;background-image:none;text-decoration:none}.introjs-disabled:focus,.introjs-disabled:hover{color:#9e9e9e;border-color:#bdbdbd;box-shadow:none;cursor:default;background-color:#f4f4f4;background-image:none;text-decoration:none}.introjs-hidden{display:none}.introjs-bullets{text-align:center;padding-top:10px;padding-bottom:10px}.introjs-bullets ul{box-sizing:content-box;clear:both;margin:0 auto 0;padding:0;display:inline-block}.introjs-bullets ul li{box-sizing:content-box;list-style:none;float:left;margin:0 2px}.introjs-bullets ul li a{transition:width .1s ease-in;box-sizing:content-box;display:block;width:6px;height:6px;background:#ccc;border-radius:10px;text-decoration:none;cursor:pointer}.introjs-bullets ul li a:focus,.introjs-bullets ul li a:hover{width:15px;background:#999;text-decoration:none;outline:0}.introjs-bullets ul li a.active{width:15px;background:#999}.introjs-progress{box-sizing:content-box;overflow:hidden;height:10px;margin:10px;border-radius:4px;background-color:#e0e0e0}.introjs-progressbar{box-sizing:content-box;float:left;width:0%;height:100%;font-size:10px;line-height:10px;text-align:center;background-color:#08c}.introjsFloatingElement{position:absolute;height:0;width:0;left:50%;top:50%}.introjs-fixedTooltip{position:fixed}.introjs-hint{box-sizing:content-box;position:absolute;background:0 0;width:20px;height:15px;cursor:pointer}.introjs-hint:focus{border:0;outline:0}.introjs-hint:hover>.introjs-hint-pulse{background-color:rgba(60,60,60,.57)}.introjs-hidehint{display:none}.introjs-fixedhint{position:fixed}@keyframes introjspulse{0%{transform:scale(0.95);box-shadow:0 0 0 0 rgba(0,0,0,.7)}70%{transform:scale(1);box-shadow:0 0 0 10px rgba(0,0,0,0)}100%{transform:scale(0.95);box-shadow:0 0 0 0 rgba(0,0,0,0)}}.introjs-hint-pulse{box-sizing:content-box;width:15px;height:15px;border-radius:30px;background-color:rgba(136,136,136,.24);z-index:10;position:absolute;transition:all .2s ease-out;animation:introjspulse 2s infinite}.introjs-hint-no-anim .introjs-hint-pulse{animation:none}.introjs-hint-dot{box-sizing:content-box;background:0 0;border-radius:60px;height:50px;width:50px;position:absolute;top:-18px;left:-18px;z-index:1;opacity:0}</style><style>.iv7ItYoe1VojQ3h_FO5M{display:flex;justify-content:center;align-items:center}</style><style>@keyframes sHe6mhLqMU8DkQOBrTZc{0%{transform:scale(1.5)}20%{transform:scale(1.2)}40%{transform:scale(1.5)}60%{transform:scale(1.2)}100%{transform:scale(1)}}.z6jLBicQHfHM18IiKQnb{cursor:pointer;background-color:#233966;box-shadow:rgba(0,0,0,.2) -8px -10px 16px -8px,rgba(0,0,0,.2) -8px 10px 16px -8px;z-index:2147483647;right:-80px;border-radius:4px 0px 0px 4px;transition:right .5s ease}.mUCGZH3WNA1WhXYwWuS6{animation:TRZac9Cb_um0GGe1UEi6 1s ease}@keyframes TRZac9Cb_um0GGe1UEi6{0%{right:-80px}100%{right:0}}.Q2NAthXAIhnjuqK80UXS{animation:XPSTDCkgbVJrbarXPCGK 1s ease}@keyframes XPSTDCkgbVJrbarXPCGK{0%{right:-80px}100%{right:-24px}}.nDnMYkPqHhoST3ySEp1a{position:absolute;right:0;top:67vh;display:flex}.witYhW1vo_BEaLBqNvzO{width:200px;border:2px solid #fff;box-shadow:0px 4px 10px rgba(64,84,153,.2);border-radius:6px;bottom:0px !important;padding:6px;position:fixed;background:#fff;right:40px}.DjPXuzOTuxzV69FZOsOy{-webkit-user-drag:none;user-select:none;-moz-user-select:none;-webkit-user-select:none;-ms-user-select:none;-webkit-user-drag:none;height:44px;max-width:none !important}.kDUcmw18hj7sVG8CKF18{border:2px solid #fff;box-shadow:0px 4px 10px rgba(64,84,153,.2);border-radius:10px;padding:1rem 2rem 2rem 2rem;position:fixed;background:#fff;right:85px;min-width:40rem}.CXeW5Ln9vKhicw7nsYc1{width:300px;border:2px solid #fff;box-shadow:0px 4px 10px rgba(64,84,153,.2);border-radius:10px;padding:5px;position:fixed;background:#fff;right:45px;bottom:10px}.DjPXuzOTuxzV69FZOsOy{-webkit-user-drag:none;user-select:none;-moz-user-select:none;-webkit-user-select:none;-ms-user-select:none;-webkit-user-drag:none}.f0PZkx0LkAwO3Y64IMkI{border:0px !important;font-size:14px !important;font-weight:400 !important;display:flex !important;align-items:center;width:100%}.f0PZkx0LkAwO3Y64IMkI:hover{background-color:#f0f6ff !important}.RtH7SuE5kBYN7ySG4r3E{background-color:#276cd2;color:#fff !important;display:flex !important;z-index:1;font-size:14px}.mEX83gqdV1j2t90EsH7F{height:50px}.PY6pDDAbcnm1BKdnBRYV{height:50px}</style><style>.HwtEDnfxs7B0QJDQjP8X{font-weight:700;letter-spacing:.01em;font-size:22px;white-space:nowrap;color:#fff}.eF21SXqOLAGrqpOgRIDR{background-color:#233966;color:#fff;display:flex;align-items:center;justify-content:space-between}.e7EovO2IRVcjiqZ9O9Rk{position:absolute;left:-38px;cursor:pointer;background:#233966;padding:13px;border-radius:10px 0 0px 10px}.e7EovO2IRVcjiqZ9O9Rk:hover{background:#152c5b}.e7EovO2IRVcjiqZ9O9Rk:active{background:#24447e}.ffxJq_eleWdiXyMOflEX{background:#fcfaf9;border-bottom:2px solid #ece4db;color:#000;height:auto;line-height:1;font-size:16px;font-weight:600}.L2uU3Yp51ZNCUfkv0cuQ{font-size:13px;color:rgba(0,0,0,.67);line-height:18px;margin-top:4px;text-rendering:optimizespeed;text-align:left}.I2kkKaJc158bO2ten2_U{position:absolute;border-radius:5px;width:200px;z-index:2;box-shadow:0px 4px 4px rgba(143,196,249,.271);background:#fff;right:20px;overflow:hidden}.rdj58KzA3YrgrUJYKGBr{padding:10px;cursor:pointer;color:#000}.rdj58KzA3YrgrUJYKGBr:hover{background:#f0f6ff}.LWB7e4obQvqsZNRXRTgy:hover{background-color:#152c5b}.LWB7e4obQvqsZNRXRTgy{cursor:pointer;border-radius:50%;height:34px;width:34px;margin-right:14px}</style><style>.ONyCd0tV8IRIG07PfMI2{display:flex;gap:10px;align-items:center;font-weight:500}.NZnWT5cjGFMExFc4XL90{display:flex;justify-content:center;flex-direction:column;height:56%;align-items:center;padding:0 3rem}.fMEpql3O2slBXczSgAv2:hover{text-decoration:underline}.AkykDtErpUJtAHQr4i4A{align-items:center;justify-content:center;background:#fff;display:flex;padding:1rem 3rem;border-radius:.5rem;cursor:pointer;border:1px solid #276cd2}.AkykDtErpUJtAHQr4i4A:hover{background:#deebff}.SFyjljpi2cbjy21VX21l{margin-top:4rem;justify-content:center;display:flex}.yev07hqupfzmgUm4Dw4w{height:12px;width:12px;margin:.5rem;border-radius:50%;cursor:pointer;background-color:#445880}.iny1wsl2wyUTrBQynclF{background-color:#508de8}</style><style>.mxCiU0v7JNhBYnYLtZy3{background-color:#fff;border-radius:4px;margin:1rem 0rem;padding:1rem;display:flex;align-items:center;gap:1rem;margin-bottom:1rem}.d4eCM3_iH310IV8gFxB7{font-size:20px;font-weight:500;margin:2rem 0}.to549bU2isdVncUuHoJp{font-weight:500}.be5_ukD99ozVUBQr8066{border:1px solid #cacfda;width:100%;padding:1rem;margin-bottom:1rem;color:#152c5b;background-color:#fff !important}.be5_ukD99ozVUBQr8066::placeholder{color:#cacfda}.be5_ukD99ozVUBQr8066:focus{border:1px solid #cacfda !important;outline:none;box-shadow:0px 0px 0px 1px rgba(0,144,237,.4)}.be5_ukD99ozVUBQr8066:hover{border:1px solid #cacfda}.D6O6E0BkhXQWXdX9K4HJ{padding:0 2rem}</style><style>.u15NCQqHzMIMsu06WqEf{font-family:"Lexed",sans-serif !important}.uk6HFaN7Km8W64h2zwcA{background-color:#edf3fd;height:100%}.CfvfO6t6d0l7zAjDL1rN{padding-top:20%;text-align:center}.LpE_2UTqK2EQSyVPOLJb{font-weight:500;font-size:17px;margin-top:6px;color:#152c5b}.ahHupRvoiR8Mjc9z6TMC{font-weight:400;font-size:12px;color:#152c5b;margin-bottom:2rem}.re26Mn0a_iUDlI9wO2e5{width:90%;margin:auto}.MEbdIboPd19h39rQjOON{cursor:pointer;padding:10px;align-items:center;box-sizing:border-box;background:#fff;border:1px solid #508de8;box-shadow:0px 4px 4px rgba(80,141,232,.2);border-radius:5px;margin-bottom:1.25rem}.MEbdIboPd19h39rQjOON:hover{background-color:#f0f6ff !important}.bOEJyjxA1KgFyy0DP9ab{color:#152c5b;font-size:15px}.yaFgZasbckZKFRU3xjbo{display:flex;justify-content:center;align-items:center}.cynwGgRFSaJJdslAAwbw{color:#152c5b !important;font-size:14px;display:flex;flex-direction:row;border-bottom:1px solid rgba(80,141,232,.3) !important;padding:1rem 0rem 1rem 2rem}.Chb8Icg05cM4oY11vRVA{padding:1.5rem;color:#152c5b !important;font-size:20px;font-weight:400;background:#e0ffe8 !important;border-radius:5px !important;margin:1rem;display:flex;flex-direction:row;align-items:center}.VyqqoFbMmgYxXanAphQI{font-size:16px;color:#152c5b !important;display:inline-block;margin-bottom:2px;outline:none !important}.pYQ18_YaKgnvO6cUCUof{padding:2rem !important;outline:none !important}.pYQ18_YaKgnvO6cUCUof .EKabOFxv50TJm4UGD__r{border:none !important;padding:8px !important;outline:none !important}.pYQ18_YaKgnvO6cUCUof .bvTj11kwDLbZVRGzFj6E{margin-bottom:16px !important;outline:none !important}.QGQ2K7kH4TtsqAxlO_wO{border:1px solid #96a0b5 !important;border-radius:3px !important;height:40px !important;padding:8px !important;outline:none !important}.VYchiNa11XPwvfGNUMmt{position:absolute;top:40px;right:0}.wL1Z3xLp9F1s6EZqpIqt{width:350px !important;background:#e1edff;padding:2rem 2rem 1rem 1rem;border-radius:15px 15px 0px 0px;bottom:0;position:fixed}.HB_K89Tyr2KR8Xk7O16l{width:90%;margin:auto;margin-top:2rem}.opewIfuOtslQVyPIgXmK{background:#4280dc;border-radius:4px;color:#fff;height:2.4rem important;box-shadow:rgba(0,0,0,.1) 0px 4px 12px}.opewIfuOtslQVyPIgXmK:hover,.opewIfuOtslQVyPIgXmK:focus,.opewIfuOtslQVyPIgXmK:active{border-color:#276cd2;background-color:#276cd2;color:#fff}</style><style>.o35bMbmPYVk64JV22miM{width:0px;height:100%;box-shadow:3px 3px 8px 8px rgba(0,0,0,.3)}.JwiAIExewhnhSEkWhcw5{width:350px !important}.haHR7Y1v05qaRVYq8WQL .zRRLhJydEwCZGfVAznmt>label,.QeKvNBtxXNp2WKRyZTx9.zRRLhJydEwCZGfVAznmt>label,.xseL7nrfXJOOhSOEz3uj.zRRLhJydEwCZGfVAznmt>label{margin:0;font-size:14px;font-weight:600}.sJKpUaxnTGFVy16lZE7p{margin-bottom:12px}#wSIa2F1Wsejss6CyR_ue .CoOTA02a92ma62E0gOQS,#wSIa2F1Wsejss6CyR_ue input[type=date],#wSIa2F1Wsejss6CyR_ue input[type=datetime-local],#wSIa2F1Wsejss6CyR_ue input[type=datetime],#wSIa2F1Wsejss6CyR_ue input[type=email],#wSIa2F1Wsejss6CyR_ue input[type=month],#wSIa2F1Wsejss6CyR_ue input[type=number],#wSIa2F1Wsejss6CyR_ue input[type=password],#wSIa2F1Wsejss6CyR_ue input[type=search],#wSIa2F1Wsejss6CyR_ue input[type=tel],#wSIa2F1Wsejss6CyR_ue input[type=text],#wSIa2F1Wsejss6CyR_ue input[type=time],#wSIa2F1Wsejss6CyR_ue input[type=url],#wSIa2F1Wsejss6CyR_ue input[type=week],#wSIa2F1Wsejss6CyR_ue select,#wSIa2F1Wsejss6CyR_ue textarea{box-shadow:none;color:#000}#wSIa2F1Wsejss6CyR_ue .CoOTA02a92ma62E0gOQS:hover{box-shadow:none}</style><style>.zyiy2zL5w7W0HNMd0eu0{height:100%}.KKaootHxSY65_2ZecHxD{height:22vh}.Insv6AqDT8mnZlSgNa9o{background-color:#276cd2;color:#fff;font-size:14px}</style><style>.ant-input-affix-wrapper{position:relative;display:inline-block;width:100%;min-width:0;padding:4px 11px;color:rgba(0,0,0,.85);font-size:14px;line-height:1.5715;background-color:#fff;background-image:none;border:1px solid #d9d9d9;border-radius:2px;transition:all .3s;display:inline-flex}.ant-input-affix-wrapper::-moz-placeholder{color:#bfbfbf;-moz-user-select:none;user-select:none}.ant-input-affix-wrapper:-ms-input-placeholder{color:#bfbfbf;-ms-user-select:none;user-select:none}.ant-input-affix-wrapper::placeholder{color:#bfbfbf;-webkit-user-select:none;-moz-user-select:none;-ms-user-select:none;user-select:none}.ant-input-affix-wrapper:-moz-placeholder-shown{text-overflow:ellipsis}.ant-input-affix-wrapper:-ms-input-placeholder{text-overflow:ellipsis}.ant-input-affix-wrapper:placeholder-shown{text-overflow:ellipsis}.ant-input-affix-wrapper:hover{border-color:#40a9ff;border-right-width:1px}.ant-input-rtl .ant-input-affix-wrapper:hover{border-right-width:0;border-left-width:1px !important}.ant-input-affix-wrapper:focus,.ant-input-affix-wrapper-focused{border-color:#40a9ff;box-shadow:0 0 0 2px rgba(24,144,255,.2);border-right-width:1px;outline:0}.ant-input-rtl .ant-input-affix-wrapper:focus,.ant-input-rtl .ant-input-affix-wrapper-focused{border-right-width:0;border-left-width:1px !important}.ant-input-affix-wrapper-disabled{color:rgba(0,0,0,.25);background-color:#f5f5f5;border-color:#d9d9d9;box-shadow:none;cursor:not-allowed;opacity:1}.ant-input-affix-wrapper-disabled:hover{border-color:#d9d9d9;border-right-width:1px}.ant-input-affix-wrapper[disabled]{color:rgba(0,0,0,.25);background-color:#f5f5f5;border-color:#d9d9d9;box-shadow:none;cursor:not-allowed;opacity:1}.ant-input-affix-wrapper[disabled]:hover{border-color:#d9d9d9;border-right-width:1px}.ant-input-affix-wrapper-borderless,.ant-input-affix-wrapper-borderless:hover,.ant-input-affix-wrapper-borderless:focus,.ant-input-affix-wrapper-borderless-focused,.ant-input-affix-wrapper-borderless-disabled,.ant-input-affix-wrapper-borderless[disabled]{background-color:rgba(0,0,0,0);border:none;box-shadow:none}textarea.ant-input-affix-wrapper{max-width:100%;height:auto;min-height:32px;line-height:1.5715;vertical-align:bottom;transition:all .3s,height 0s}.ant-input-affix-wrapper-lg{padding:6.5px 11px;font-size:16px}.ant-input-affix-wrapper-sm{padding:0px 7px}.ant-input-affix-wrapper-rtl{direction:rtl}.ant-input-affix-wrapper:not(.ant-input-affix-wrapper-disabled):hover{border-color:#40a9ff;border-right-width:1px;z-index:1}.ant-input-rtl .ant-input-affix-wrapper:not(.ant-input-affix-wrapper-disabled):hover{border-right-width:0;border-left-width:1px !important}.ant-input-search-with-button .ant-input-affix-wrapper:not(.ant-input-affix-wrapper-disabled):hover{z-index:0}.ant-input-affix-wrapper-focused,.ant-input-affix-wrapper:focus{z-index:1}.ant-input-affix-wrapper-disabled .ant-input[disabled]{background:rgba(255,255,255,0)}.ant-input-affix-wrapper>.ant-input{font-size:inherit;border:none;outline:none}.ant-input-affix-wrapper>.ant-input:focus{box-shadow:none !important}.ant-input-affix-wrapper>.ant-input:not(textarea){padding:0}.ant-input-affix-wrapper::before{width:0;visibility:hidden;content:"&nbsp;"}.ant-input-prefix,.ant-input-suffix{display:flex;flex:none;align-items:center}.ant-input-prefix>*:not(:last-child),.ant-input-suffix>*:not(:last-child){margin-right:8px}.ant-input-show-count-suffix{color:rgba(0,0,0,.45)}.ant-input-show-count-has-suffix{margin-right:2px}.ant-input-prefix{margin-right:4px}.ant-input-suffix{margin-left:4px}.anticon.ant-input-clear-icon,.ant-input-clear-icon{margin:0;color:rgba(0,0,0,.25);font-size:12px;vertical-align:-1px;cursor:pointer;transition:color .3s}.anticon.ant-input-clear-icon:hover,.ant-input-clear-icon:hover{color:rgba(0,0,0,.45)}.anticon.ant-input-clear-icon:active,.ant-input-clear-icon:active{color:rgba(0,0,0,.85)}.anticon.ant-input-clear-icon-hidden,.ant-input-clear-icon-hidden{visibility:hidden}.anticon.ant-input-clear-icon-has-suffix,.ant-input-clear-icon-has-suffix{margin:0 4px}.ant-input-affix-wrapper.ant-input-affix-wrapper-textarea-with-clear-btn{padding:0}.ant-input-affix-wrapper.ant-input-affix-wrapper-textarea-with-clear-btn .ant-input-clear-icon{position:absolute;top:8px;right:8px;z-index:1}.ant-input-status-error:not(.ant-input-disabled):not(.ant-input-borderless).ant-input,.ant-input-status-error:not(.ant-input-disabled):not(.ant-input-borderless).ant-input:hover{background:#fff;border-color:#ff4d4f}.ant-input-status-error:not(.ant-input-disabled):not(.ant-input-borderless).ant-input:focus,.ant-input-status-error:not(.ant-input-disabled):not(.ant-input-borderless).ant-input-focused{border-color:#ff7875;box-shadow:0 0 0 2px rgba(255,77,79,.2);border-right-width:1px;outline:0}.ant-input-status-error .ant-input-prefix{color:#ff4d4f}.ant-input-status-warning:not(.ant-input-disabled):not(.ant-input-borderless).ant-input,.ant-input-status-warning:not(.ant-input-disabled):not(.ant-input-borderless).ant-input:hover{background:#fff;border-color:#faad14}.ant-input-status-warning:not(.ant-input-disabled):not(.ant-input-borderless).ant-input:focus,.ant-input-status-warning:not(.ant-input-disabled):not(.ant-input-borderless).ant-input-focused{border-color:#ffc53d;box-shadow:0 0 0 2px rgba(250,173,20,.2);border-right-width:1px;outline:0}.ant-input-status-warning .ant-input-prefix{color:#faad14}.ant-input-affix-wrapper-status-error:not(.ant-input-affix-wrapper-disabled):not(.ant-input-affix-wrapper-borderless).ant-input-affix-wrapper,.ant-input-affix-wrapper-status-error:not(.ant-input-affix-wrapper-disabled):not(.ant-input-affix-wrapper-borderless).ant-input-affix-wrapper:hover{background:#fff;border-color:#ff4d4f}.ant-input-affix-wrapper-status-error:not(.ant-input-affix-wrapper-disabled):not(.ant-input-affix-wrapper-borderless).ant-input-affix-wrapper:focus,.ant-input-affix-wrapper-status-error:not(.ant-input-affix-wrapper-disabled):not(.ant-input-affix-wrapper-borderless).ant-input-affix-wrapper-focused{border-color:#ff7875;box-shadow:0 0 0 2px rgba(255,77,79,.2);border-right-width:1px;outline:0}.ant-input-affix-wrapper-status-error .ant-input-prefix{color:#ff4d4f}.ant-input-affix-wrapper-status-warning:not(.ant-input-affix-wrapper-disabled):not(.ant-input-affix-wrapper-borderless).ant-input-affix-wrapper,.ant-input-affix-wrapper-status-warning:not(.ant-input-affix-wrapper-disabled):not(.ant-input-affix-wrapper-borderless).ant-input-affix-wrapper:hover{background:#fff;border-color:#faad14}.ant-input-affix-wrapper-status-warning:not(.ant-input-affix-wrapper-disabled):not(.ant-input-affix-wrapper-borderless).ant-input-affix-wrapper:focus,.ant-input-affix-wrapper-status-warning:not(.ant-input-affix-wrapper-disabled):not(.ant-input-affix-wrapper-borderless).ant-input-affix-wrapper-focused{border-color:#ffc53d;box-shadow:0 0 0 2px rgba(250,173,20,.2);border-right-width:1px;outline:0}.ant-input-affix-wrapper-status-warning .ant-input-prefix{color:#faad14}.ant-input-textarea-status-error.ant-input-textarea-has-feedback .ant-input,.ant-input-textarea-status-warning.ant-input-textarea-has-feedback .ant-input,.ant-input-textarea-status-success.ant-input-textarea-has-feedback .ant-input,.ant-input-textarea-status-validating.ant-input-textarea-has-feedback .ant-input{padding-right:24px}.ant-input-group-wrapper-status-error .ant-input-group-addon{color:#ff4d4f;border-color:#ff4d4f}.ant-input-group-wrapper-status-warning .ant-input-group-addon{color:#faad14;border-color:#faad14}.ant-input{box-sizing:border-box;margin:0;padding:0;font-variant:tabular-nums;list-style:none;font-feature-settings:"tnum";position:relative;display:inline-block;width:100%;min-width:0;padding:4px 11px;color:rgba(0,0,0,.85);font-size:14px;line-height:1.5715;background-color:#fff;background-image:none;border:1px solid #d9d9d9;border-radius:2px;transition:all .3s}.ant-input::-moz-placeholder{color:#bfbfbf;-moz-user-select:none;user-select:none}.ant-input:-ms-input-placeholder{color:#bfbfbf;-ms-user-select:none;user-select:none}.ant-input::placeholder{color:#bfbfbf;-webkit-user-select:none;-moz-user-select:none;-ms-user-select:none;user-select:none}.ant-input:-moz-placeholder-shown{text-overflow:ellipsis}.ant-input:-ms-input-placeholder{text-overflow:ellipsis}.ant-input:placeholder-shown{text-overflow:ellipsis}.ant-input:hover{border-color:#40a9ff;border-right-width:1px}.ant-input-rtl .ant-input:hover{border-right-width:0;border-left-width:1px !important}.ant-input:focus,.ant-input-focused{border-color:#40a9ff;box-shadow:0 0 0 2px rgba(24,144,255,.2);border-right-width:1px;outline:0}.ant-input-rtl .ant-input:focus,.ant-input-rtl .ant-input-focused{border-right-width:0;border-left-width:1px !important}.ant-input-disabled{color:rgba(0,0,0,.25);background-color:#f5f5f5;border-color:#d9d9d9;box-shadow:none;cursor:not-allowed;opacity:1}.ant-input-disabled:hover{border-color:#d9d9d9;border-right-width:1px}.ant-input[disabled]{color:rgba(0,0,0,.25);background-color:#f5f5f5;border-color:#d9d9d9;box-shadow:none;cursor:not-allowed;opacity:1}.ant-input[disabled]:hover{border-color:#d9d9d9;border-right-width:1px}.ant-input-borderless,.ant-input-borderless:hover,.ant-input-borderless:focus,.ant-input-borderless-focused,.ant-input-borderless-disabled,.ant-input-borderless[disabled]{background-color:rgba(0,0,0,0);border:none;box-shadow:none}textarea.ant-input{max-width:100%;height:auto;min-height:32px;line-height:1.5715;vertical-align:bottom;transition:all .3s,height 0s}.ant-input-lg{padding:6.5px 11px;font-size:16px}.ant-input-sm{padding:0px 7px}.ant-input-rtl{direction:rtl}.ant-input-group{box-sizing:border-box;margin:0;padding:0;color:rgba(0,0,0,.85);font-size:14px;font-variant:tabular-nums;line-height:1.5715;list-style:none;font-feature-settings:"tnum";position:relative;display:table;width:100%;border-collapse:separate;border-spacing:0}.ant-input-group[class*=col-]{float:none;padding-right:0;padding-left:0}.ant-input-group>[class*=col-]{padding-right:8px}.ant-input-group>[class*=col-]:last-child{padding-right:0}.ant-input-group-addon,.ant-input-group-wrap,.ant-input-group>.ant-input{display:table-cell}.ant-input-group-addon:not(:first-child):not(:last-child),.ant-input-group-wrap:not(:first-child):not(:last-child),.ant-input-group>.ant-input:not(:first-child):not(:last-child){border-radius:0}.ant-input-group-addon,.ant-input-group-wrap{width:1px;white-space:nowrap;vertical-align:middle}.ant-input-group-wrap>*{display:block !important}.ant-input-group .ant-input{float:left;width:100%;margin-bottom:0;text-align:inherit}.ant-input-group .ant-input:focus{z-index:1;border-right-width:1px}.ant-input-group .ant-input:hover{z-index:1;border-right-width:1px}.ant-input-search-with-button .ant-input-group .ant-input:hover{z-index:0}.ant-input-group-addon{position:relative;padding:0 11px;color:rgba(0,0,0,.85);font-weight:normal;font-size:14px;text-align:center;background-color:#fafafa;border:1px solid #d9d9d9;border-radius:2px;transition:all .3s}.ant-input-group-addon .ant-select{margin:-5px -11px}.ant-input-group-addon .ant-select.ant-select-single:not(.ant-select-customize-input) .ant-select-selector{background-color:inherit;border:1px solid rgba(0,0,0,0);box-shadow:none}.ant-input-group-addon .ant-select-open .ant-select-selector,.ant-input-group-addon .ant-select-focused .ant-select-selector{color:#1890ff}.ant-input-group-addon .ant-cascader-picker{margin:-9px -12px;background-color:rgba(0,0,0,0)}.ant-input-group-addon .ant-cascader-picker .ant-cascader-input{text-align:left;border:0;box-shadow:none}.ant-input-group>.ant-input:first-child,.ant-input-group-addon:first-child{border-top-right-radius:0;border-bottom-right-radius:0}.ant-input-group>.ant-input:first-child .ant-select .ant-select-selector,.ant-input-group-addon:first-child .ant-select .ant-select-selector{border-top-right-radius:0;border-bottom-right-radius:0}.ant-input-group>.ant-input-affix-wrapper:not(:first-child) .ant-input{border-top-left-radius:0;border-bottom-left-radius:0}.ant-input-group>.ant-input-affix-wrapper:not(:last-child) .ant-input{border-top-right-radius:0;border-bottom-right-radius:0}.ant-input-group-addon:first-child{border-right:0}.ant-input-group-addon:last-child{border-left:0}.ant-input-group>.ant-input:last-child,.ant-input-group-addon:last-child{border-top-left-radius:0;border-bottom-left-radius:0}.ant-input-group>.ant-input:last-child .ant-select .ant-select-selector,.ant-input-group-addon:last-child .ant-select .ant-select-selector{border-top-left-radius:0;border-bottom-left-radius:0}.ant-input-group-lg .ant-input,.ant-input-group-lg>.ant-input-group-addon{padding:6.5px 11px;font-size:16px}.ant-input-group-sm .ant-input,.ant-input-group-sm>.ant-input-group-addon{padding:0px 7px}.ant-input-group-lg .ant-select-single .ant-select-selector{height:40px}.ant-input-group-sm .ant-select-single .ant-select-selector{height:24px}.ant-input-group .ant-input-affix-wrapper:not(:last-child){border-top-right-radius:0;border-bottom-right-radius:0}.ant-input-search .ant-input-group .ant-input-affix-wrapper:not(:last-child){border-top-left-radius:2px;border-bottom-left-radius:2px}.ant-input-group .ant-input-affix-wrapper:not(:first-child),.ant-input-search .ant-input-group .ant-input-affix-wrapper:not(:first-child){border-top-left-radius:0;border-bottom-left-radius:0}.ant-input-group.ant-input-group-compact{display:block}.ant-input-group.ant-input-group-compact::before{display:table;content:""}.ant-input-group.ant-input-group-compact::after{display:table;clear:both;content:""}.ant-input-group.ant-input-group-compact-addon:not(:first-child):not(:last-child),.ant-input-group.ant-input-group-compact-wrap:not(:first-child):not(:last-child),.ant-input-group.ant-input-group-compact>.ant-input:not(:first-child):not(:last-child){border-right-width:1px}.ant-input-group.ant-input-group-compact-addon:not(:first-child):not(:last-child):hover,.ant-input-group.ant-input-group-compact-wrap:not(:first-child):not(:last-child):hover,.ant-input-group.ant-input-group-compact>.ant-input:not(:first-child):not(:last-child):hover{z-index:1}.ant-input-group.ant-input-group-compact-addon:not(:first-child):not(:last-child):focus,.ant-input-group.ant-input-group-compact-wrap:not(:first-child):not(:last-child):focus,.ant-input-group.ant-input-group-compact>.ant-input:not(:first-child):not(:last-child):focus{z-index:1}.ant-input-group.ant-input-group-compact>*{display:inline-block;float:none;vertical-align:top;border-radius:0}.ant-input-group.ant-input-group-compact>.ant-input-affix-wrapper{display:inline-flex}.ant-input-group.ant-input-group-compact>.ant-picker-range{display:inline-flex}.ant-input-group.ant-input-group-compact>*:not(:last-child){margin-right:-1px;border-right-width:1px}.ant-input-group.ant-input-group-compact .ant-input{float:none}.ant-input-group.ant-input-group-compact>.ant-select>.ant-select-selector,.ant-input-group.ant-input-group-compact>.ant-select-auto-complete .ant-input,.ant-input-group.ant-input-group-compact>.ant-cascader-picker .ant-input,.ant-input-group.ant-input-group-compact>.ant-input-group-wrapper .ant-input{border-right-width:1px;border-radius:0}.ant-input-group.ant-input-group-compact>.ant-select>.ant-select-selector:hover,.ant-input-group.ant-input-group-compact>.ant-select-auto-complete .ant-input:hover,.ant-input-group.ant-input-group-compact>.ant-cascader-picker .ant-input:hover,.ant-input-group.ant-input-group-compact>.ant-input-group-wrapper .ant-input:hover{z-index:1}.ant-input-group.ant-input-group-compact>.ant-select>.ant-select-selector:focus,.ant-input-group.ant-input-group-compact>.ant-select-auto-complete .ant-input:focus,.ant-input-group.ant-input-group-compact>.ant-cascader-picker .ant-input:focus,.ant-input-group.ant-input-group-compact>.ant-input-group-wrapper .ant-input:focus{z-index:1}.ant-input-group.ant-input-group-compact>.ant-select-focused{z-index:1}.ant-input-group.ant-input-group-compact>.ant-select>.ant-select-arrow{z-index:1}.ant-input-group.ant-input-group-compact>*:first-child,.ant-input-group.ant-input-group-compact>.ant-select:first-child>.ant-select-selector,.ant-input-group.ant-input-group-compact>.ant-select-auto-complete:first-child .ant-input,.ant-input-group.ant-input-group-compact>.ant-cascader-picker:first-child .ant-input{border-top-left-radius:2px;border-bottom-left-radius:2px}.ant-input-group.ant-input-group-compact>*:last-child,.ant-input-group.ant-input-group-compact>.ant-select:last-child>.ant-select-selector,.ant-input-group.ant-input-group-compact>.ant-cascader-picker:last-child .ant-input,.ant-input-group.ant-input-group-compact>.ant-cascader-picker-focused:last-child .ant-input{border-right-width:1px;border-top-right-radius:2px;border-bottom-right-radius:2px}.ant-input-group.ant-input-group-compact>.ant-select-auto-complete .ant-input{vertical-align:top}.ant-input-group.ant-input-group-compact .ant-input-group-wrapper+.ant-input-group-wrapper{margin-left:-1px}.ant-input-group.ant-input-group-compact .ant-input-group-wrapper+.ant-input-group-wrapper .ant-input-affix-wrapper{border-radius:0}.ant-input-group.ant-input-group-compact .ant-input-group-wrapper:not(:last-child).ant-input-search>.ant-input-group>.ant-input-group-addon>.ant-input-search-button{border-radius:0}.ant-input-group.ant-input-group-compact .ant-input-group-wrapper:not(:last-child).ant-input-search>.ant-input-group>.ant-input{border-radius:2px 0 0 2px}.ant-input-group>.ant-input-rtl:first-child,.ant-input-group-rtl .ant-input-group-addon:first-child{border-radius:0 2px 2px 0}.ant-input-group-rtl .ant-input-group-addon:first-child{border-right:1px solid #d9d9d9;border-left:0}.ant-input-group-rtl .ant-input-group-addon:last-child{border-right:0;border-left:1px solid #d9d9d9;border-radius:2px 0 0 2px}.ant-input-group-rtl.ant-input-group>.ant-input:last-child,.ant-input-group-rtl.ant-input-group-addon:last-child{border-radius:2px 0 0 2px}.ant-input-group-rtl.ant-input-group .ant-input-affix-wrapper:not(:first-child){border-radius:2px 0 0 2px}.ant-input-group-rtl.ant-input-group .ant-input-affix-wrapper:not(:last-child){border-radius:0 2px 2px 0}.ant-input-group-rtl.ant-input-group.ant-input-group-compact>*:not(:last-child){margin-right:0;margin-left:-1px;border-left-width:1px}.ant-input-group-rtl.ant-input-group.ant-input-group-compact>*:first-child,.ant-input-group-rtl.ant-input-group.ant-input-group-compact>.ant-select:first-child>.ant-select-selector,.ant-input-group-rtl.ant-input-group.ant-input-group-compact>.ant-select-auto-complete:first-child .ant-input,.ant-input-group-rtl.ant-input-group.ant-input-group-compact>.ant-cascader-picker:first-child .ant-input{border-radius:0 2px 2px 0}.ant-input-group-rtl.ant-input-group.ant-input-group-compact>*:last-child,.ant-input-group-rtl.ant-input-group.ant-input-group-compact>.ant-select:last-child>.ant-select-selector,.ant-input-group-rtl.ant-input-group.ant-input-group-compact>.ant-select-auto-complete:last-child .ant-input,.ant-input-group-rtl.ant-input-group.ant-input-group-compact>.ant-cascader-picker:last-child .ant-input,.ant-input-group-rtl.ant-input-group.ant-input-group-compact>.ant-cascader-picker-focused:last-child .ant-input{border-left-width:1px;border-radius:2px 0 0 2px}.ant-input-group.ant-input-group-compact .ant-input-group-wrapper-rtl+.ant-input-group-wrapper-rtl{margin-right:-1px;margin-left:0}.ant-input-group.ant-input-group-compact .ant-input-group-wrapper-rtl:not(:last-child).ant-input-search>.ant-input-group>.ant-input{border-radius:0 2px 2px 0}.ant-input-group-wrapper{display:inline-block;width:100%;text-align:start;vertical-align:top}.ant-input-password-icon.anticon{color:rgba(0,0,0,.45);cursor:pointer;transition:all .3s}.ant-input-password-icon.anticon:hover{color:rgba(0,0,0,.85)}.ant-input[type=color]{height:32px}.ant-input[type=color].ant-input-lg{height:40px}.ant-input[type=color].ant-input-sm{height:24px;padding-top:3px;padding-bottom:3px}.ant-input-textarea-show-count>.ant-input{height:100%}.ant-input-textarea-show-count::after{float:right;color:rgba(0,0,0,.45);white-space:nowrap;content:attr(data-count);pointer-events:none}.ant-input-textarea-show-count.ant-input-textarea-in-form-item::after{margin-bottom:-22px}.ant-input-textarea-suffix{position:absolute;top:0;right:11px;bottom:0;z-index:1;display:inline-flex;align-items:center;margin:auto}.ant-input-compact-item:not(.ant-input-compact-last-item):not(.ant-input-compact-item-rtl){margin-right:-1px}.ant-input-compact-item:not(.ant-input-compact-last-item).ant-input-compact-item-rtl{margin-left:-1px}.ant-input-compact-item:hover,.ant-input-compact-item:focus,.ant-input-compact-item:active{z-index:2}.ant-input-compact-item[disabled]{z-index:0}.ant-input-compact-item:not(.ant-input-compact-first-item):not(.ant-input-compact-last-item).ant-input{border-radius:0}.ant-input-compact-item.ant-input.ant-input-compact-first-item:not(.ant-input-compact-last-item):not(.ant-input-compact-item-rtl){border-top-right-radius:0;border-bottom-right-radius:0}.ant-input-compact-item.ant-input.ant-input-compact-last-item:not(.ant-input-compact-first-item):not(.ant-input-compact-item-rtl){border-top-left-radius:0;border-bottom-left-radius:0}.ant-input-compact-item.ant-input.ant-input-compact-item-rtl.ant-input-compact-first-item:not(.ant-input-compact-last-item){border-top-left-radius:0;border-bottom-left-radius:0}.ant-input-compact-item.ant-input.ant-input-compact-item-rtl.ant-input-compact-last-item:not(.ant-input-compact-first-item){border-top-right-radius:0;border-bottom-right-radius:0}.ant-input-search .ant-input:hover,.ant-input-search .ant-input:focus{border-color:#40a9ff}.ant-input-search .ant-input:hover+.ant-input-group-addon .ant-input-search-button:not(.ant-btn-primary),.ant-input-search .ant-input:focus+.ant-input-group-addon .ant-input-search-button:not(.ant-btn-primary){border-left-color:#40a9ff}.ant-input-search .ant-input-affix-wrapper{border-radius:0}.ant-input-search .ant-input-lg{line-height:1.5713}.ant-input-search>.ant-input-group>.ant-input-group-addon:last-child{left:-1px;padding:0;border:0}.ant-input-search>.ant-input-group>.ant-input-group-addon:last-child .ant-input-search-button{padding-top:0;padding-bottom:0;border-radius:0 2px 2px 0}.ant-input-search>.ant-input-group>.ant-input-group-addon:last-child .ant-input-search-button:not(.ant-btn-primary){color:rgba(0,0,0,.45)}.ant-input-search>.ant-input-group>.ant-input-group-addon:last-child .ant-input-search-button:not(.ant-btn-primary).ant-btn-loading::before{top:0;right:0;bottom:0;left:0}.ant-input-search-button{height:32px}.ant-input-search-button:hover,.ant-input-search-button:focus{z-index:1}.ant-input-search-large .ant-input-search-button{height:40px}.ant-input-search-small .ant-input-search-button{height:24px}.ant-input-search.ant-input-compact-item:not(.ant-input-compact-item-rtl):not(.ant-input-compact-last-item) .ant-input-group-addon .ant-input-search-button{margin-right:-1px;border-radius:0}.ant-input-search.ant-input-compact-item:not(.ant-input-compact-first-item) .ant-input,.ant-input-search.ant-input-compact-item:not(.ant-input-compact-first-item) .ant-input-affix-wrapper{border-radius:0}.ant-input-search.ant-input-compact-item>.ant-input-group-addon .ant-input-search-button:hover,.ant-input-search.ant-input-compact-item>.ant-input:hover,.ant-input-search.ant-input-compact-item .ant-input-affix-wrapper:hover,.ant-input-search.ant-input-compact-item>.ant-input-group-addon .ant-input-search-button:focus,.ant-input-search.ant-input-compact-item>.ant-input:focus,.ant-input-search.ant-input-compact-item .ant-input-affix-wrapper:focus,.ant-input-search.ant-input-compact-item>.ant-input-group-addon .ant-input-search-button:active,.ant-input-search.ant-input-compact-item>.ant-input:active,.ant-input-search.ant-input-compact-item .ant-input-affix-wrapper:active{z-index:2}.ant-input-search.ant-input-compact-item>.ant-input-affix-wrapper-focused{z-index:2}.ant-input-search.ant-input-compact-item-rtl:not(.ant-input-compact-last-item) .ant-input-group-addon:last-child .ant-input-search-button{margin-left:-1px;border-radius:0}.ant-input-group-wrapper-rtl{direction:rtl}.ant-input-group-rtl{direction:rtl}.ant-input-affix-wrapper.ant-input-affix-wrapper-rtl>input.ant-input{border:none;outline:none}.ant-input-affix-wrapper-rtl .ant-input-prefix{margin:0 0 0 4px}.ant-input-affix-wrapper-rtl .ant-input-suffix{margin:0 4px 0 0}.ant-input-textarea-rtl{direction:rtl}.ant-input-textarea-rtl.ant-input-textarea-show-count::after{text-align:left}.ant-input-affix-wrapper-rtl .ant-input-clear-icon-has-suffix{margin-right:0;margin-left:4px}.ant-input-affix-wrapper-rtl .ant-input-clear-icon{right:auto;left:8px}.ant-input-search-rtl{direction:rtl}.ant-input-search-rtl .ant-input:hover+.ant-input-group-addon .ant-input-search-button:not(.ant-btn-primary),.ant-input-search-rtl .ant-input:focus+.ant-input-group-addon .ant-input-search-button:not(.ant-btn-primary){border-left-color:#d9d9d9}.ant-input-search-rtl .ant-input:hover+.ant-input-group-addon .ant-input-search-button:not(.ant-btn-primary):hover,.ant-input-search-rtl .ant-input:focus+.ant-input-group-addon .ant-input-search-button:not(.ant-btn-primary):hover{border-left-color:#40a9ff}.ant-input-search-rtl>.ant-input-group>.ant-input-affix-wrapper:hover,.ant-input-search-rtl>.ant-input-group>.ant-input-affix-wrapper-focused{border-right-color:#40a9ff}.ant-input-search-rtl>.ant-input-group>.ant-input-group-addon:last-child{right:-1px;left:auto}.ant-input-search-rtl>.ant-input-group>.ant-input-group-addon:last-child .ant-input-search-button{border-radius:2px 0 0 2px}@media screen and (-ms-high-contrast: active),(-ms-high-contrast: none){.ant-input{height:32px}.ant-input-lg{height:40px}.ant-input-sm{height:24px}.ant-input-affix-wrapper>input.ant-input{height:auto}}</style><style>.GRyQMYliblyZ3UiCIfFT{text-align:center;width:100%;padding:2rem}.GRyQMYliblyZ3UiCIfFT>*{margin-bottom:1rem}.Gu6ZV2KfOJIyRCT1C2TH{text-align:center;height:90%;overflow:auto}.uEpi193deoe1XcZMT59P{width:95%;background:#152c5b;color:#fff;bottom:0;position:absolute;margin:0 1rem 0 1rem;padding:1rem;border-radius:1rem 1rem 0 0}</style><style>.EyRl37VAVV7Qu0r9AL0K{padding:1rem}.QnwXLeoHgyBlVa26SYRM{margin:1rem 0;border-radius:6px;padding:1.5rem 2rem;border:1px solid #e1edff;display:flex;justify-content:space-between}.x3Qb6HB9QZGZgVZYY4T2{align-items:center;display:flex;gap:1rem}.xFkwftF6oC7kz2gyXveM{height:100%;display:flex;flex-direction:column;overflow:auto;font-size:14px;background-color:#fff}.xFkwftF6oC7kz2gyXveM ul,ol{padding-left:1.5rem}.QdmW4dhXGafg3cO5vOdf{font-weight:500;font-size:large;padding-bottom:.5rem}.d059O8J2MXz12a3Gived{margin-top:auto;display:flex;background:#152c5b;color:#fff;margin:auto 1rem 0rem;padding:1rem;gap:2rem;justify-content:center;border-radius:1rem 1rem 0 0;align-items:center}.Nfu0hPS90y_P2aYr3_PZ{background:#305093;padding:.8rem;display:flex;border-radius:4px}.Nfu0hPS90y_P2aYr3_PZ:hover{background:#445880}.Nfu0hPS90y_P2aYr3_PZ:active{background:#24447e}.cd1eVj_5W2Qbqx1EohjA{display:flex;gap:1rem;padding-bottom:.5rem;align-items:center}</style><style>.F_hwddTIaeS8dapTcF6V{text-align:center;width:100%;padding:2rem}.F_hwddTIaeS8dapTcF6V>*{margin-bottom:1rem}.GbRPaeTYC7xX7iFog6BP{text-align:center;height:90%;overflow:auto}.zOluK39XdPq1C33oFWAp{width:95%;background:#152c5b;color:#fff;bottom:0;position:absolute;margin:0 1rem 0 1rem;padding:1rem;border-radius:1rem 1rem 0 0}</style><style>.MabtQ_wElx_8rd5xopxZ{height:100%;width:100%;position:absolute;background-color:rgba(0,0,0,.4);display:flex;align-items:center;justify-content:center}.McPzbKmuJsbLO6FOcDFv{padding:1rem;background-color:#fff;display:flex;justify-content:center;height:50%;text-align:center;align-items:center;border-radius:10px;border:2px solid #fff}.GaP4FkAvh2ik_ATnjH4x{display:flex;width:70%;flex-direction:column;align-items:center;gap:1rem;padding:4rem 0}</style><style>.y4BeOS_tZ7fbnZjx266s{display:flex}.mOVgk9yxdsnKrMMHQXIC{padding:1rem;border:1px solid #e1edff;display:flex;align-items:center;font-weight:500;cursor:pointer}</style><style>.cuvy0MqivxIaDrmPz5_V{padding:1rem}.tucieJZwRi_jrEBV5j8T:hover{border:1px solid rgba(80,141,232,.5)}.tucieJZwRi_jrEBV5j8T{margin:1rem 0;border-radius:6px;padding:1.5rem 2rem;border:1px solid #e1edff;display:flex;justify-content:space-between;cursor:pointer}.SDPdn78VGXb2rAy8BXMy{align-items:center;display:flex;gap:1rem}.obi3helDnFZZNULGBYhR{background:rgba(255,255,0,.5);padding:1rem;border:1px rgba(255,165,0,.8) solid;margin:0 .5rem}.KzposB0RrNMk1rOmE4xt{text-align:center;background:#152c5b;color:#fff;padding:2rem;border-radius:0 0 2rem 2rem;align-items:center}.wxz_7Ji4FWPux4GpNPv6{display:flex;background:#152c5b;color:#fff;padding:1rem;justify-content:center;border-radius:0 0 2rem 2rem;align-items:center}.KIk7L3sUgOo_JtKJzH8Q{font-size:20px;font-weight:400}.aSXbkpJ4R__qH1SPm0OZ{margin-top:auto;display:flex;background:#152c5b;color:#fff;margin:auto 1rem 0rem;padding:1rem;justify-content:space-around;border-radius:1rem 1rem 0 0;align-items:center}.RxakcrD16uPT3doKbk08{background:#305093;padding:.8rem;display:flex;border-radius:4px;color:#fff !important}.RxakcrD16uPT3doKbk08:hover{background:#445880}.RxakcrD16uPT3doKbk08:active{background:#24447e}.fb61A27DkVvNxi9eoS_I{border:1px solid #e1edff;border-radius:5px;display:flex;gap:1rem;position:relative;padding:2rem;background-color:#fff;margin-bottom:2rem}.kA3EfAFeobDMr7TTv3t8{text-align:center;cursor:pointer;margin-top:3px}.kA3EfAFeobDMr7TTv3t8:hover{color:#1890ff}</style><style>.FH76K6rPcEWnIG3gyD9M ::-webkit-scrollbar{width:5px}.FH76K6rPcEWnIG3gyD9M ::-webkit-scrollbar-track{background:#f1f1f1}.FH76K6rPcEWnIG3gyD9M ::-webkit-scrollbar-thumb{background:#888}.FH76K6rPcEWnIG3gyD9M ::-webkit-scrollbar-thumb:hover{background:#555}.FH76K6rPcEWnIG3gyD9M body,.FH76K6rPcEWnIG3gyD9M p{color:#152c5b !important}.FH76K6rPcEWnIG3gyD9M h5{font-weight:500 !important;padding:1rem 0 !important}.FH76K6rPcEWnIG3gyD9M .m5vyNt_4Y2LBwI1Xqk8X,.FH76K6rPcEWnIG3gyD9M .Do6lzB45L_qVXy0hGiEm,.FH76K6rPcEWnIG3gyD9M .FH76K6rPcEWnIG3gyD9M .pis8rLfXg053rqqlV5y2,.FH76K6rPcEWnIG3gyD9M .aq9BMumd5SU63J26heFf,.FH76K6rPcEWnIG3gyD9M blockquote,.FH76K6rPcEWnIG3gyD9M body,.FH76K6rPcEWnIG3gyD9M h1,.FH76K6rPcEWnIG3gyD9M h2,.FH76K6rPcEWnIG3gyD9M h3,.FH76K6rPcEWnIG3gyD9M h4,.FH76K6rPcEWnIG3gyD9M h5,.FH76K6rPcEWnIG3gyD9M p{color:#152c5b !important}.FH76K6rPcEWnIG3gyD9M{width:0px;background-color:#f8fbfe;height:100%;color:#152c5b !important}.FH76K6rPcEWnIG3gyD9M p{font-size:14px}.gE2cdLkys7Jjnbmfn6tT{width:400px !important}.UCghUnR60yLNgX5r89ii{align-items:center;justify-content:center;background:#fff;display:flex;padding:1rem 3rem;border-radius:.5rem;cursor:pointer;border:1px solid #276cd2}.UCghUnR60yLNgX5r89ii:hover{background:#deebff}.UOW6Kati1VXD8ep92I3t{display:flex;gap:10px;align-items:center;font-weight:500}.UiOWs4g4iU9kehcrxZ23{width:6px;height:6px;background-color:#a8c6f4;margin:0 .5rem}.qVvPUJCnt59Mauot9WUj{display:flex;justify-content:center;flex-direction:column;height:56%;align-items:center;padding:0 3rem}._1GULDTSFUorpwoRodifw:hover{text-decoration:underline}.L_HjS3He5UpKfcW8WnCo{display:flex;flex-direction:column;justify-content:center;gap:1rem;align-items:center;height:100%;overflow:auto;padding:0 5rem;text-align:center}</style><style>.ant-notification{box-sizing:border-box;margin:0;padding:0;color:rgba(0,0,0,.85);font-size:14px;font-variant:tabular-nums;line-height:1.5715;list-style:none;font-feature-settings:"tnum";position:fixed;z-index:1010;margin-right:24px}.ant-notification-close-icon{font-size:14px;cursor:pointer}.ant-notification-hook-holder{position:relative}.ant-notification-notice{position:relative;width:384px;max-width:calc(100vw - 48px);margin-bottom:16px;margin-left:auto;padding:16px 24px;overflow:hidden;line-height:1.5715;word-wrap:break-word;background:#fff;border-radius:2px;box-shadow:0 3px 6px -4px rgba(0,0,0,.12),0 6px 16px 0 rgba(0,0,0,.08),0 9px 28px 8px rgba(0,0,0,.05)}.ant-notification-top .ant-notification-notice,.ant-notification-bottom .ant-notification-notice{margin-right:auto;margin-left:auto}.ant-notification-topLeft .ant-notification-notice,.ant-notification-bottomLeft .ant-notification-notice{margin-right:auto;margin-left:0}.ant-notification-notice-message{margin-bottom:8px;color:rgba(0,0,0,.85);font-size:16px;line-height:24px}.ant-notification-notice-message-single-line-auto-margin{display:block;width:calc(264px - 100%);max-width:4px;background-color:rgba(0,0,0,0);pointer-events:none}.ant-notification-notice-message-single-line-auto-margin::before{display:block;content:""}.ant-notification-notice-description{font-size:14px}.ant-notification-notice-closable .ant-notification-notice-message{padding-right:24px}.ant-notification-notice-with-icon .ant-notification-notice-message{margin-bottom:4px;margin-left:48px;font-size:16px}.ant-notification-notice-with-icon .ant-notification-notice-description{margin-left:48px;font-size:14px}.ant-notification-notice-icon{position:absolute;margin-left:4px;font-size:24px;line-height:24px}.anticon.ant-notification-notice-icon-success{color:#52c41a}.anticon.ant-notification-notice-icon-info{color:#1890ff}.anticon.ant-notification-notice-icon-warning{color:#faad14}.anticon.ant-notification-notice-icon-error{color:#ff4d4f}.ant-notification-notice-close{position:absolute;top:16px;right:22px;color:rgba(0,0,0,.45);outline:none}.ant-notification-notice-close:hover{color:rgba(0,0,0,.67)}.ant-notification-notice-btn{float:right;margin-top:16px}.ant-notification .notification-fade-effect{animation-duration:.24s;animation-timing-function:cubic-bezier(0.645, 0.045, 0.355, 1);animation-fill-mode:both}.ant-notification-fade-enter,.ant-notification-fade-appear{animation-duration:.24s;animation-timing-function:cubic-bezier(0.645, 0.045, 0.355, 1);animation-fill-mode:both;opacity:0;animation-play-state:paused}.ant-notification-fade-leave{animation-duration:.24s;animation-timing-function:cubic-bezier(0.645, 0.045, 0.355, 1);animation-fill-mode:both;animation-duration:.2s;animation-play-state:paused}.ant-notification-fade-enter.ant-notification-fade-enter-active,.ant-notification-fade-appear.ant-notification-fade-appear-active{animation-name:NotificationFadeIn;animation-play-state:running}.ant-notification-fade-leave.ant-notification-fade-leave-active{animation-name:NotificationFadeOut;animation-play-state:running}@keyframes NotificationFadeIn{0%{left:384px;opacity:0}100%{left:0;opacity:1}}@keyframes NotificationFadeOut{0%{max-height:150px;margin-bottom:16px;opacity:1}100%{max-height:0;margin-bottom:0;padding-top:0;padding-bottom:0;opacity:0}}.ant-notification-rtl{direction:rtl}.ant-notification-rtl .ant-notification-notice-closable .ant-notification-notice-message{padding-right:0;padding-left:24px}.ant-notification-rtl .ant-notification-notice-with-icon .ant-notification-notice-message{margin-right:48px;margin-left:0}.ant-notification-rtl .ant-notification-notice-with-icon .ant-notification-notice-description{margin-right:48px;margin-left:0}.ant-notification-rtl .ant-notification-notice-icon{margin-right:4px;margin-left:0}.ant-notification-rtl .ant-notification-notice-close{right:auto;left:22px}.ant-notification-rtl .ant-notification-notice-btn{float:left}.ant-notification-top,.ant-notification-bottom{margin-right:0;margin-left:0}.ant-notification-top .ant-notification-fade-enter.ant-notification-fade-enter-active,.ant-notification-top .ant-notification-fade-appear.ant-notification-fade-appear-active{animation-name:NotificationTopFadeIn}.ant-notification-bottom .ant-notification-fade-enter.ant-notification-fade-enter-active,.ant-notification-bottom .ant-notification-fade-appear.ant-notification-fade-appear-active{animation-name:NotificationBottomFadeIn}.ant-notification-topLeft,.ant-notification-bottomLeft{margin-right:0;margin-left:24px}.ant-notification-topLeft .ant-notification-fade-enter.ant-notification-fade-enter-active,.ant-notification-bottomLeft .ant-notification-fade-enter.ant-notification-fade-enter-active,.ant-notification-topLeft .ant-notification-fade-appear.ant-notification-fade-appear-active,.ant-notification-bottomLeft .ant-notification-fade-appear.ant-notification-fade-appear-active{animation-name:NotificationLeftFadeIn}@keyframes NotificationTopFadeIn{0%{margin-top:-100%;opacity:0}100%{margin-top:0;opacity:1}}@keyframes NotificationBottomFadeIn{0%{margin-bottom:-100%;opacity:0}100%{margin-bottom:0;opacity:1}}@keyframes NotificationLeftFadeIn{0%{right:384px;opacity:0}100%{right:0;opacity:1}}</style><style>.O4DiB7wjFO3axUSimpuO ::-webkit-scrollbar{width:8px}.O4DiB7wjFO3axUSimpuO ::-webkit-scrollbar-track{background:#f1f1f1;display:none}.O4DiB7wjFO3axUSimpuO ::-webkit-scrollbar-thumb{background:rgba(0,0,0,.3)}.O4DiB7wjFO3axUSimpuO ::-webkit-scrollbar-thumb:hover{background:rgba(0,0,0,.5)}.O4DiB7wjFO3axUSimpuO body,.O4DiB7wjFO3axUSimpuO p{color:#152c5b !important}.O4DiB7wjFO3axUSimpuO .rX1o4EH6Mt6d6JVw7Q4_,.O4DiB7wjFO3axUSimpuO .wHpil1UhCDmtr5n86ii0,.O4DiB7wjFO3axUSimpuO .O4DiB7wjFO3axUSimpuO .dLbqF6NJP2r1OygJqup5,.O4DiB7wjFO3axUSimpuO .RbM80RlC2iciI774pD0q,.O4DiB7wjFO3axUSimpuO blockquote,.O4DiB7wjFO3axUSimpuO body,.O4DiB7wjFO3axUSimpuO h1,.O4DiB7wjFO3axUSimpuO h2,.O4DiB7wjFO3axUSimpuO h3,.O4DiB7wjFO3axUSimpuO h4,.O4DiB7wjFO3axUSimpuO h5,.O4DiB7wjFO3axUSimpuO p{color:#152c5b !important}.O4DiB7wjFO3axUSimpuO{width:0px;background-color:#f8fbfe;height:100%;color:#152c5b !important;box-shadow:3px 3px 8px 8px rgba(0,0,0,.3)}.O4DiB7wjFO3axUSimpuO p{font-size:14px}.j9HSvKdWia1V5Iy9cad8{width:400px !important}.KRWFpSLclxafrqHqZQCO{align-items:center;justify-content:center;background:#fff;display:flex;padding:1rem 3rem;border-radius:.5rem;cursor:pointer;border:1px solid #276cd2}.KRWFpSLclxafrqHqZQCO:hover{background:#deebff}.Vbjr8UN728NNEE3SAKgr{display:flex;gap:10px;align-items:center;font-weight:500}.zF34C2qpWIb2BzYAbvmG{width:6px;height:6px;background-color:#a8c6f4;margin:0 .5rem}.t2Xt7XOMOp7FTGJVWPX3{display:flex;justify-content:center;flex-direction:column;height:56%;align-items:center;padding:0 3rem}.vCYCbwZxUrKV7OBC67Vx:hover{text-decoration:underline}.sIbamB_BI4dk0ABhkC74{display:flex;flex-direction:column;justify-content:center;gap:1rem;align-items:center;height:100%;overflow:auto;padding:0 5rem;text-align:center}</style><style>.Gl1LytS7IKm0kbznepy9{position:fixed;right:0px;top:0px;z-index:2147483647;color:#152c5b;font-size:14px !important;box-sizing:border-box;background:#f8fbfe;height:100vh}</style></head>

  <body class="logged-in env-production page-responsive page-blob intent-mouse" style="word-wrap: break-word;">
    <div data-turbo-body="" class="logged-in env-production page-responsive page-blob" style="word-wrap: break-word;">
      


    <div class="position-relative js-header-wrapper ">
      <a href="#start-of-content" class="p-3 color-bg-accent-emphasis color-fg-on-emphasis show-on-focus js-skip-to-content">Skip to content</a>
      <span data-view-component="true" class="progress-pjax-loader Progress position-fixed width-full">
    <span style="width: 0%;" data-view-component="true" class="Progress-item progress-pjax-loader-bar left-0 top-0 color-bg-accent-emphasis"></span>
</span>      
      


        <script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/vendors-node_modules_allex_crc32_lib_crc32_esm_js-node_modules_github_mini-throttle_dist_deco-26fa0f-02e7ed68dae1.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/vendors-node_modules_github_clipboard-copy-element_dist_index_esm_js-node_modules_delegated-e-b37f7d-a9177ba414f2.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/app_assets_modules_github_command-palette_items_help-item_ts-app_assets_modules_github_comman-48ad9d-beffe41c24a7.js"></script>
<script crossorigin="anonymous" defer="defer" type="application/javascript" src="https://github.githubassets.com/assets/command-palette-c2a5f7e7eb12.js"></script>

            <header class="Header js-details-container Details px-3 px-md-4 px-lg-5 flex-wrap flex-md-nowrap" role="banner">

    <div class="Header-item mt-n1 mb-n1  d-none d-md-flex">
      <a class="Header-link" href="https://github.com/" data-hotkey="g d" aria-label="Homepage " data-turbo="false" data-analytics-event="{&quot;category&quot;:&quot;Header&quot;,&quot;action&quot;:&quot;go to dashboard&quot;,&quot;label&quot;:&quot;icon:logo&quot;}">
  <svg height="32" aria-hidden="true" viewBox="0 0 16 16" version="1.1" width="32" data-view-component="true" class="octicon octicon-mark-github v-align-middle">
    <path d="M8 0c4.42 0 8 3.58 8 8a8.013 8.013 0 0 1-5.45 7.59c-.4.08-.55-.17-.55-.38 0-.27.01-1.13.01-2.2 0-.75-.25-1.23-.54-1.48 1.78-.2 3.65-.88 3.65-3.95 0-.88-.31-1.59-.82-2.15.08-.2.36-1.02-.08-2.12 0 0-.67-.22-2.2.82-.64-.18-1.32-.27-2-.27-.68 0-1.36.09-2 .27-1.53-1.03-2.2-.82-2.2-.82-.44 1.1-.16 1.92-.08 2.12-.51.56-.82 1.28-.82 2.15 0 3.06 1.86 3.75 3.64 3.95-.23.2-.44.55-.51 1.07-.46.21-1.61.55-2.33-.66-.15-.24-.6-.83-1.23-.82-.67.01-.27.38.01.53.34.19.73.9.82 1.13.16.45.68 1.31 2.69.94 0 .67.01 1.3.01 1.49 0 .21-.15.45-.55.38A7.995 7.995 0 0 1 0 8c0-4.42 3.58-8 8-8Z"></path>
</svg>
</a>

    </div>

    <div class="Header-item d-md-none">
        <button aria-label="Toggle navigation" aria-expanded="false" type="button" data-view-component="true" class="Header-link js-details-target btn-link">    <svg aria-hidden="true" height="24" viewBox="0 0 16 16" version="1.1" width="24" data-view-component="true" class="octicon octicon-three-bars">
    <path d="M1 2.75A.75.75 0 0 1 1.75 2h12.5a.75.75 0 0 1 0 1.5H1.75A.75.75 0 0 1 1 2.75Zm0 5A.75.75 0 0 1 1.75 7h12.5a.75.75 0 0 1 0 1.5H1.75A.75.75 0 0 1 1 7.75ZM1.75 12h12.5a.75.75 0 0 1 0 1.5H1.75a.75.75 0 0 1 0-1.5Z"></path>
</svg>
</button>    </div>

    <div class="Header-item Header-item--full flex-column flex-md-row width-full flex-order-2 flex-md-order-none mr-0 mt-3 mt-md-0 Details-content--hidden-not-important d-md-flex">
              



<div class="header-search flex-auto position-relative js-site-search flex-self-stretch flex-md-self-auto mb-3 mb-md-0 mr-0 mr-md-3 scoped-search site-scoped-search js-jump-to">
  <div class="position-relative">
    <!-- '"` --><!-- </textarea></xmp> --><form class="js-site-search-form" role="search" aria-label="Site" data-scope-type="Repository" data-scope-id="34100441" data-scoped-search-url="/bbottema/simple-java-mail/search" data-owner-scoped-search-url="/users/bbottema/search" data-unscoped-search-url="/search" data-turbo="false" action="/bbottema/simple-java-mail/search" accept-charset="UTF-8" method="get">
      <label class="form-control header-search-wrapper input-sm p-0 js-chromeless-input-container header-search-wrapper-jump-to position-relative d-flex flex-justify-between flex-items-center">
        <input type="text" class="form-control js-site-search-focus header-search-input jump-to-field js-jump-to-field js-site-search-field is-clearable" data-hotkey="s,/" name="q" placeholder="Search or jump to…" data-unscoped-placeholder="Search or jump to…" data-scoped-placeholder="Search or jump to…" autocapitalize="off" role="combobox" aria-haspopup="listbox" aria-expanded="false" aria-autocomplete="list" aria-controls="jump-to-results" aria-label="Search or jump to…" data-jump-to-suggestions-path="/_graphql/GetSuggestedNavigationDestinations" spellcheck="false" autocomplete="off">
        <input type="hidden" value="6m7VdW3zIq3CGrGpL35nrzGhC24mZMFdgXRaJ3_Tnu4IYb-AY3dLXp7GChjKi3gYsPk-OKuSUCPC093cENxaFQ" data-csrf="true" class="js-data-jump-to-suggestions-path-csrf">
        <input type="hidden" class="js-site-search-type-field" name="type">
            <svg xmlns="http://www.w3.org/2000/svg" width="22" height="20" aria-hidden="true" class="mr-1 header-search-key-slash"><path fill="none" stroke="#979A9C" opacity=".4" d="M3.5.5h12c1.7 0 3 1.3 3 3v13c0 1.7-1.3 3-3 3h-12c-1.7 0-3-1.3-3-3v-13c0-1.7 1.3-3 3-3z"></path><path fill="#979A9C" d="M11.8 6L8 15.1h-.9L10.8 6h1z"></path></svg>


          <div class="Box position-absolute overflow-hidden d-none jump-to-suggestions js-jump-to-suggestions-container">
            
<ul class="d-none js-jump-to-suggestions-template-container">
  

<li class="d-flex flex-justify-start flex-items-center p-0 f5 navigation-item js-navigation-item js-jump-to-suggestion" role="option">
  <a tabindex="-1" class="no-underline d-flex flex-auto flex-items-center jump-to-suggestions-path js-jump-to-suggestion-path js-navigation-open p-2" href="" data-item-type="suggestion">
    <div class="jump-to-octicon js-jump-to-octicon flex-shrink-0 mr-2 text-center d-none">
      <svg title="Repository" aria-label="Repository" role="img" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-repo js-jump-to-octicon-repo d-none flex-shrink-0">
    <path d="M2 2.5A2.5 2.5 0 0 1 4.5 0h8.75a.75.75 0 0 1 .75.75v12.5a.75.75 0 0 1-.75.75h-2.5a.75.75 0 0 1 0-1.5h1.75v-2h-8a1 1 0 0 0-.714 1.7.75.75 0 1 1-1.072 1.05A2.495 2.495 0 0 1 2 11.5Zm10.5-1h-8a1 1 0 0 0-1 1v6.708A2.486 2.486 0 0 1 4.5 9h8ZM5 12.25a.25.25 0 0 1 .25-.25h3.5a.25.25 0 0 1 .25.25v3.25a.25.25 0 0 1-.4.2l-1.45-1.087a.249.249 0 0 0-.3 0L5.4 15.7a.25.25 0 0 1-.4-.2Z"></path>
</svg>
      <svg title="Project" aria-label="Project" role="img" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-project js-jump-to-octicon-project d-none flex-shrink-0">
    <path d="M1.75 0h12.5C15.216 0 16 .784 16 1.75v12.5A1.75 1.75 0 0 1 14.25 16H1.75A1.75 1.75 0 0 1 0 14.25V1.75C0 .784.784 0 1.75 0ZM1.5 1.75v12.5c0 .138.112.25.25.25h12.5a.25.25 0 0 0 .25-.25V1.75a.25.25 0 0 0-.25-.25H1.75a.25.25 0 0 0-.25.25ZM11.75 3a.75.75 0 0 1 .75.75v7.5a.75.75 0 0 1-1.5 0v-7.5a.75.75 0 0 1 .75-.75Zm-8.25.75a.75.75 0 0 1 1.5 0v5.5a.75.75 0 0 1-1.5 0ZM8 3a.75.75 0 0 1 .75.75v3.5a.75.75 0 0 1-1.5 0v-3.5A.75.75 0 0 1 8 3Z"></path>
</svg>
      <svg title="Search" aria-label="Search" role="img" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-search js-jump-to-octicon-search d-none flex-shrink-0">
    <path d="M10.68 11.74a6 6 0 0 1-7.922-8.982 6 6 0 0 1 8.982 7.922l3.04 3.04a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215ZM11.5 7a4.499 4.499 0 1 0-8.997 0A4.499 4.499 0 0 0 11.5 7Z"></path>
</svg>
    </div>

    <img class="avatar mr-2 flex-shrink-0 js-jump-to-suggestion-avatar d-none" alt="" aria-label="Team" src="" width="28" height="28">

    <div class="jump-to-suggestion-name js-jump-to-suggestion-name flex-auto overflow-hidden text-left no-wrap css-truncate css-truncate-target">
    </div>

    <div class="border rounded-2 flex-shrink-0 color-bg-subtle px-1 color-fg-muted ml-1 f6 d-none js-jump-to-badge-search">
      <span class="js-jump-to-badge-search-text-default d-none" aria-label="in this repository">
        In this repository
      </span>
      <span class="js-jump-to-badge-search-text-global d-none" aria-label="in all of GitHub">
        All GitHub
      </span>
      <span aria-hidden="true" class="d-inline-block ml-1 v-align-middle">↵</span>
    </div>

    <div aria-hidden="true" class="border rounded-2 flex-shrink-0 color-bg-subtle px-1 color-fg-muted ml-1 f6 d-none d-on-nav-focus js-jump-to-badge-jump">
      Jump to
      <span class="d-inline-block ml-1 v-align-middle">↵</span>
    </div>
  </a>
</li>

</ul>

<ul class="d-none js-jump-to-no-results-template-container">
  <li class="d-flex flex-justify-center flex-items-center f5 d-none js-jump-to-suggestion p-2">
    <span class="color-fg-muted">No suggested jump to results</span>
  </li>
</ul>

<ul id="jump-to-results" role="listbox" class="p-0 m-0 js-navigation-container jump-to-suggestions-results-container js-jump-to-suggestions-results-container">
  

<li class="d-flex flex-justify-start flex-items-center p-0 f5 navigation-item js-navigation-item js-jump-to-scoped-search d-none" role="option">
  <a tabindex="-1" class="no-underline d-flex flex-auto flex-items-center jump-to-suggestions-path js-jump-to-suggestion-path js-navigation-open p-2" href="" data-item-type="scoped_search">
    <div class="jump-to-octicon js-jump-to-octicon flex-shrink-0 mr-2 text-center d-none">
      <svg title="Repository" aria-label="Repository" role="img" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-repo js-jump-to-octicon-repo d-none flex-shrink-0">
    <path d="M2 2.5A2.5 2.5 0 0 1 4.5 0h8.75a.75.75 0 0 1 .75.75v12.5a.75.75 0 0 1-.75.75h-2.5a.75.75 0 0 1 0-1.5h1.75v-2h-8a1 1 0 0 0-.714 1.7.75.75 0 1 1-1.072 1.05A2.495 2.495 0 0 1 2 11.5Zm10.5-1h-8a1 1 0 0 0-1 1v6.708A2.486 2.486 0 0 1 4.5 9h8ZM5 12.25a.25.25 0 0 1 .25-.25h3.5a.25.25 0 0 1 .25.25v3.25a.25.25 0 0 1-.4.2l-1.45-1.087a.249.249 0 0 0-.3 0L5.4 15.7a.25.25 0 0 1-.4-.2Z"></path>
</svg>
      <svg title="Project" aria-label="Project" role="img" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-project js-jump-to-octicon-project d-none flex-shrink-0">
    <path d="M1.75 0h12.5C15.216 0 16 .784 16 1.75v12.5A1.75 1.75 0 0 1 14.25 16H1.75A1.75 1.75 0 0 1 0 14.25V1.75C0 .784.784 0 1.75 0ZM1.5 1.75v12.5c0 .138.112.25.25.25h12.5a.25.25 0 0 0 .25-.25V1.75a.25.25 0 0 0-.25-.25H1.75a.25.25 0 0 0-.25.25ZM11.75 3a.75.75 0 0 1 .75.75v7.5a.75.75 0 0 1-1.5 0v-7.5a.75.75 0 0 1 .75-.75Zm-8.25.75a.75.75 0 0 1 1.5 0v5.5a.75.75 0 0 1-1.5 0ZM8 3a.75.75 0 0 1 .75.75v3.5a.75.75 0 0 1-1.5 0v-3.5A.75.75 0 0 1 8 3Z"></path>
</svg>
      <svg title="Search" aria-label="Search" role="img" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-search js-jump-to-octicon-search d-none flex-shrink-0">
    <path d="M10.68 11.74a6 6 0 0 1-7.922-8.982 6 6 0 0 1 8.982 7.922l3.04 3.04a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215ZM11.5 7a4.499 4.499 0 1 0-8.997 0A4.499 4.499 0 0 0 11.5 7Z"></path>
</svg>
    </div>

    <img class="avatar mr-2 flex-shrink-0 js-jump-to-suggestion-avatar d-none" alt="" aria-label="Team" src="" width="28" height="28">

    <div class="jump-to-suggestion-name js-jump-to-suggestion-name flex-auto overflow-hidden text-left no-wrap css-truncate css-truncate-target">
    </div>

    <div class="border rounded-2 flex-shrink-0 color-bg-subtle px-1 color-fg-muted ml-1 f6 d-none js-jump-to-badge-search">
      <span class="js-jump-to-badge-search-text-default d-none" aria-label="in this repository">
        In this repository
      </span>
      <span class="js-jump-to-badge-search-text-global d-none" aria-label="in all of GitHub">
        All GitHub
      </span>
      <span aria-hidden="true" class="d-inline-block ml-1 v-align-middle">↵</span>
    </div>

    <div aria-hidden="true" class="border rounded-2 flex-shrink-0 color-bg-subtle px-1 color-fg-muted ml-1 f6 d-none d-on-nav-focus js-jump-to-badge-jump">
      Jump to
      <span class="d-inline-block ml-1 v-align-middle">↵</span>
    </div>
  </a>
</li>

  

<li class="d-flex flex-justify-start flex-items-center p-0 f5 navigation-item js-navigation-item js-jump-to-owner-scoped-search d-none" role="option">
  <a tabindex="-1" class="no-underline d-flex flex-auto flex-items-center jump-to-suggestions-path js-jump-to-suggestion-path js-navigation-open p-2" href="" data-item-type="owner_scoped_search">
    <div class="jump-to-octicon js-jump-to-octicon flex-shrink-0 mr-2 text-center d-none">
      <svg title="Repository" aria-label="Repository" role="img" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-repo js-jump-to-octicon-repo d-none flex-shrink-0">
    <path d="M2 2.5A2.5 2.5 0 0 1 4.5 0h8.75a.75.75 0 0 1 .75.75v12.5a.75.75 0 0 1-.75.75h-2.5a.75.75 0 0 1 0-1.5h1.75v-2h-8a1 1 0 0 0-.714 1.7.75.75 0 1 1-1.072 1.05A2.495 2.495 0 0 1 2 11.5Zm10.5-1h-8a1 1 0 0 0-1 1v6.708A2.486 2.486 0 0 1 4.5 9h8ZM5 12.25a.25.25 0 0 1 .25-.25h3.5a.25.25 0 0 1 .25.25v3.25a.25.25 0 0 1-.4.2l-1.45-1.087a.249.249 0 0 0-.3 0L5.4 15.7a.25.25 0 0 1-.4-.2Z"></path>
</svg>
      <svg title="Project" aria-label="Project" role="img" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-project js-jump-to-octicon-project d-none flex-shrink-0">
    <path d="M1.75 0h12.5C15.216 0 16 .784 16 1.75v12.5A1.75 1.75 0 0 1 14.25 16H1.75A1.75 1.75 0 0 1 0 14.25V1.75C0 .784.784 0 1.75 0ZM1.5 1.75v12.5c0 .138.112.25.25.25h12.5a.25.25 0 0 0 .25-.25V1.75a.25.25 0 0 0-.25-.25H1.75a.25.25 0 0 0-.25.25ZM11.75 3a.75.75 0 0 1 .75.75v7.5a.75.75 0 0 1-1.5 0v-7.5a.75.75 0 0 1 .75-.75Zm-8.25.75a.75.75 0 0 1 1.5 0v5.5a.75.75 0 0 1-1.5 0ZM8 3a.75.75 0 0 1 .75.75v3.5a.75.75 0 0 1-1.5 0v-3.5A.75.75 0 0 1 8 3Z"></path>
</svg>
      <svg title="Search" aria-label="Search" role="img" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-search js-jump-to-octicon-search d-none flex-shrink-0">
    <path d="M10.68 11.74a6 6 0 0 1-7.922-8.982 6 6 0 0 1 8.982 7.922l3.04 3.04a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215ZM11.5 7a4.499 4.499 0 1 0-8.997 0A4.499 4.499 0 0 0 11.5 7Z"></path>
</svg>
    </div>

    <img class="avatar mr-2 flex-shrink-0 js-jump-to-suggestion-avatar d-none" alt="" aria-label="Team" src="" width="28" height="28">

    <div class="jump-to-suggestion-name js-jump-to-suggestion-name flex-auto overflow-hidden text-left no-wrap css-truncate css-truncate-target">
    </div>

    <div class="border rounded-2 flex-shrink-0 color-bg-subtle px-1 color-fg-muted ml-1 f6 d-none js-jump-to-badge-search">
      <span class="js-jump-to-badge-search-text-default d-none" aria-label="in this user">
        In this user
      </span>
      <span class="js-jump-to-badge-search-text-global d-none" aria-label="in all of GitHub">
        All GitHub
      </span>
      <span aria-hidden="true" class="d-inline-block ml-1 v-align-middle">↵</span>
    </div>

    <div aria-hidden="true" class="border rounded-2 flex-shrink-0 color-bg-subtle px-1 color-fg-muted ml-1 f6 d-none d-on-nav-focus js-jump-to-badge-jump">
      Jump to
      <span class="d-inline-block ml-1 v-align-middle">↵</span>
    </div>
  </a>
</li>

  

<li class="d-flex flex-justify-start flex-items-center p-0 f5 navigation-item js-navigation-item js-jump-to-global-search d-none" role="option">
  <a tabindex="-1" class="no-underline d-flex flex-auto flex-items-center jump-to-suggestions-path js-jump-to-suggestion-path js-navigation-open p-2" href="" data-item-type="global_search">
    <div class="jump-to-octicon js-jump-to-octicon flex-shrink-0 mr-2 text-center d-none">
      <svg title="Repository" aria-label="Repository" role="img" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-repo js-jump-to-octicon-repo d-none flex-shrink-0">
    <path d="M2 2.5A2.5 2.5 0 0 1 4.5 0h8.75a.75.75 0 0 1 .75.75v12.5a.75.75 0 0 1-.75.75h-2.5a.75.75 0 0 1 0-1.5h1.75v-2h-8a1 1 0 0 0-.714 1.7.75.75 0 1 1-1.072 1.05A2.495 2.495 0 0 1 2 11.5Zm10.5-1h-8a1 1 0 0 0-1 1v6.708A2.486 2.486 0 0 1 4.5 9h8ZM5 12.25a.25.25 0 0 1 .25-.25h3.5a.25.25 0 0 1 .25.25v3.25a.25.25 0 0 1-.4.2l-1.45-1.087a.249.249 0 0 0-.3 0L5.4 15.7a.25.25 0 0 1-.4-.2Z"></path>
</svg>
      <svg title="Project" aria-label="Project" role="img" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-project js-jump-to-octicon-project d-none flex-shrink-0">
    <path d="M1.75 0h12.5C15.216 0 16 .784 16 1.75v12.5A1.75 1.75 0 0 1 14.25 16H1.75A1.75 1.75 0 0 1 0 14.25V1.75C0 .784.784 0 1.75 0ZM1.5 1.75v12.5c0 .138.112.25.25.25h12.5a.25.25 0 0 0 .25-.25V1.75a.25.25 0 0 0-.25-.25H1.75a.25.25 0 0 0-.25.25ZM11.75 3a.75.75 0 0 1 .75.75v7.5a.75.75 0 0 1-1.5 0v-7.5a.75.75 0 0 1 .75-.75Zm-8.25.75a.75.75 0 0 1 1.5 0v5.5a.75.75 0 0 1-1.5 0ZM8 3a.75.75 0 0 1 .75.75v3.5a.75.75 0 0 1-1.5 0v-3.5A.75.75 0 0 1 8 3Z"></path>
</svg>
      <svg title="Search" aria-label="Search" role="img" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-search js-jump-to-octicon-search d-none flex-shrink-0">
    <path d="M10.68 11.74a6 6 0 0 1-7.922-8.982 6 6 0 0 1 8.982 7.922l3.04 3.04a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215ZM11.5 7a4.499 4.499 0 1 0-8.997 0A4.499 4.499 0 0 0 11.5 7Z"></path>
</svg>
    </div>

    <img class="avatar mr-2 flex-shrink-0 js-jump-to-suggestion-avatar d-none" alt="" aria-label="Team" src="" width="28" height="28">

    <div class="jump-to-suggestion-name js-jump-to-suggestion-name flex-auto overflow-hidden text-left no-wrap css-truncate css-truncate-target">
    </div>

    <div class="border rounded-2 flex-shrink-0 color-bg-subtle px-1 color-fg-muted ml-1 f6 d-none js-jump-to-badge-search">
      <span class="js-jump-to-badge-search-text-default d-none" aria-label="in this repository">
        In this repository
      </span>
      <span class="js-jump-to-badge-search-text-global d-none" aria-label="in all of GitHub">
        All GitHub
      </span>
      <span aria-hidden="true" class="d-inline-block ml-1 v-align-middle">↵</span>
    </div>

    <div aria-hidden="true" class="border rounded-2 flex-shrink-0 color-bg-subtle px-1 color-fg-muted ml-1 f6 d-none d-on-nav-focus js-jump-to-badge-jump">
      Jump to
      <span class="d-inline-block ml-1 v-align-middle">↵</span>
    </div>
  </a>
</li>


    <li class="d-flex flex-justify-center flex-items-center p-0 f5 js-jump-to-suggestion">
      <svg style="box-sizing: content-box; color: var(--color-icon-primary);" width="32" height="32" viewBox="0 0 16 16" fill="none" data-view-component="true" class="m-3 anim-rotate">
  <circle cx="8" cy="8" r="7" stroke="currentColor" stroke-opacity="0.25" stroke-width="2" vector-effect="non-scaling-stroke"></circle>
  <path d="M15 8a7.002 7.002 0 00-7-7" stroke="currentColor" stroke-width="2" stroke-linecap="round" vector-effect="non-scaling-stroke"></path>
</svg>
    </li>
</ul>

          </div>
      </label>
</form>  </div>
</div>

        <nav id="global-nav" class="d-flex flex-column flex-md-row flex-self-stretch flex-md-self-auto" aria-label="Global">
    <a class="Header-link py-md-3 d-block d-md-none py-2 border-top border-md-top-0 border-white-fade" data-ga-click="Header, click, Nav menu - item:dashboard:user" aria-label="Dashboard" data-turbo="false" href="/dashboard">Dashboard</a>

  <a class="js-selected-navigation-item Header-link mt-md-n3 mb-md-n3 py-2 py-md-3 mr-0 mr-md-3 border-top border-md-top-0 border-white-fade" data-hotkey="g p" data-ga-click="Header, click, Nav menu - item:pulls context:user" aria-label="Pull requests you created" data-turbo="false" data-selected-links="/pulls /pulls/assigned /pulls/mentioned /pulls" href="/pulls">
      Pull<span class="d-inline d-md-none d-lg-inline"> request</span>s
</a>
  <a class="js-selected-navigation-item Header-link mt-md-n3 mb-md-n3 py-2 py-md-3 mr-0 mr-md-3 border-top border-md-top-0 border-white-fade" data-hotkey="g i" data-ga-click="Header, click, Nav menu - item:issues context:user" aria-label="Issues you created" data-turbo="false" data-selected-links="/issues /issues/assigned /issues/mentioned /issues" href="/issues">Issues</a>

      <a class="js-selected-navigation-item Header-link mt-md-n3 mb-md-n3 py-2 py-md-3 mr-0 mr-md-3 border-top border-md-top-0 border-white-fade" data-ga-click="Header, click, Nav menu - item:workspaces context:user" data-turbo="false" data-selected-links="/codespaces /codespaces" href="/codespaces">Codespaces</a>

    <div class="d-flex position-relative">
      <a class="js-selected-navigation-item Header-link flex-auto mt-md-n3 mb-md-n3 py-2 py-md-3 mr-0 mr-md-3 border-top border-md-top-0 border-white-fade" data-ga-click="Header, click, Nav menu - item:marketplace context:user" data-octo-click="marketplace_click" data-octo-dimensions="location:nav_bar" data-turbo="false" data-selected-links=" /marketplace" href="/marketplace">Marketplace</a>
    </div>

  <a class="js-selected-navigation-item Header-link mt-md-n3 mb-md-n3 py-2 py-md-3 mr-0 mr-md-3 border-top border-md-top-0 border-white-fade" data-ga-click="Header, click, Nav menu - item:explore" data-turbo="false" data-selected-links="/explore /trending /trending/developers /integrations /integrations/feature/code /integrations/feature/collaborate /integrations/feature/ship showcases showcases_search showcases_landing /explore" href="/explore">Explore</a>

      <a class="js-selected-navigation-item Header-link d-block d-md-none py-2 py-md-3 border-top border-md-top-0 border-white-fade" data-ga-click="Header, click, Nav menu - item:Sponsors" data-hydro-click="{&quot;event_type&quot;:&quot;sponsors.button_click&quot;,&quot;payload&quot;:{&quot;button&quot;:&quot;HEADER_SPONSORS_DASHBOARD&quot;,&quot;sponsorable_login&quot;:&quot;S230306&quot;,&quot;originating_url&quot;:&quot;https://github.com/bbottema/simple-java-mail/blob/master/README.md&quot;,&quot;user_id&quot;:99464989}}" data-hydro-click-hmac="2b5317d16aec3e874e87f5b693b7202ff102bafc5c5dcbf8433e8821045ce96a" data-turbo="false" data-selected-links=" /sponsors/accounts" href="/sponsors/accounts">Sponsors</a>

    <a class="Header-link d-block d-md-none mr-0 mr-md-3 py-2 py-md-3 border-top border-md-top-0 border-white-fade" data-turbo="false" href="/settings/profile">Settings</a>

    <a class="Header-link d-block d-md-none mr-0 mr-md-3 py-2 py-md-3 border-top border-md-top-0 border-white-fade" data-turbo="false" href="/S230306">
      <img class="avatar avatar-user" loading="lazy" decoding="async" src="https://avatars.githubusercontent.com/u/99464989?s=40&amp;v=4" width="20" height="20" alt="@S230306">
      S230306
</a>
    <!-- '"` --><!-- </textarea></xmp> --><form data-turbo="false" action="/logout" accept-charset="UTF-8" method="post"><input type="hidden" name="authenticity_token" value="DooAobcluZN1qCLd2uG2WvUreUMlLN-bAp2cAuX-PsvPzwfponGSFFb7ziZBhz9-tinarGkNFJbJNKSgRRW2sQ">
      <button type="submit" class="Header-link mr-0 mr-md-3 py-2 py-md-3 border-top border-md-top-0 border-white-fade d-md-none btn-link d-block width-full text-left" style="padding-left: 2px;" data-analytics-event="{&quot;category&quot;:&quot;Header&quot;,&quot;action&quot;:&quot;sign out&quot;,&quot;label&quot;:&quot;icon:logout&quot;}">
        <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-sign-out v-align-middle">
    <path d="M2 2.75C2 1.784 2.784 1 3.75 1h2.5a.75.75 0 0 1 0 1.5h-2.5a.25.25 0 0 0-.25.25v10.5c0 .138.112.25.25.25h2.5a.75.75 0 0 1 0 1.5h-2.5A1.75 1.75 0 0 1 2 13.25Zm10.44 4.5-1.97-1.97a.749.749 0 0 1 .326-1.275.749.749 0 0 1 .734.215l3.25 3.25a.75.75 0 0 1 0 1.06l-3.25 3.25a.749.749 0 0 1-1.275-.326.749.749 0 0 1 .215-.734l1.97-1.97H6.75a.75.75 0 0 1 0-1.5Z"></path>
</svg>
        Sign out
      </button>
</form></nav>

    </div>

    <div class="Header-item Header-item--full flex-justify-center d-md-none position-relative">
        <a class="Header-link" href="https://github.com/" data-hotkey="g d" aria-label="Homepage " data-turbo="false" data-analytics-event="{&quot;category&quot;:&quot;Header&quot;,&quot;action&quot;:&quot;go to dashboard&quot;,&quot;label&quot;:&quot;icon:logo&quot;}">
  <svg height="32" aria-hidden="true" viewBox="0 0 16 16" version="1.1" width="32" data-view-component="true" class="octicon octicon-mark-github v-align-middle">
    <path d="M8 0c4.42 0 8 3.58 8 8a8.013 8.013 0 0 1-5.45 7.59c-.4.08-.55-.17-.55-.38 0-.27.01-1.13.01-2.2 0-.75-.25-1.23-.54-1.48 1.78-.2 3.65-.88 3.65-3.95 0-.88-.31-1.59-.82-2.15.08-.2.36-1.02-.08-2.12 0 0-.67-.22-2.2.82-.64-.18-1.32-.27-2-.27-.68 0-1.36.09-2 .27-1.53-1.03-2.2-.82-2.2-.82-.44 1.1-.16 1.92-.08 2.12-.51.56-.82 1.28-.82 2.15 0 3.06 1.86 3.75 3.64 3.95-.23.2-.44.55-.51 1.07-.46.21-1.61.55-2.33-.66-.15-.24-.6-.83-1.23-.82-.67.01-.27.38.01.53.34.19.73.9.82 1.13.16.45.68 1.31 2.69.94 0 .67.01 1.3.01 1.49 0 .21-.15.45-.55.38A7.995 7.995 0 0 1 0 8c0-4.42 3.58-8 8-8Z"></path>
</svg>
</a>

    </div>

    <div class="Header-item mr-0 mr-md-3 flex-order-1 flex-md-order-none">
        

<notification-indicator data-channel="eyJjIjoibm90aWZpY2F0aW9uLWNoYW5nZWQ6OTk0NjQ5ODkiLCJ0IjoxNjgzMTA5OTI2fQ==--24b89ae96e98da2581d4d0eacf63a027d908d712c2c489cf35ccaad056603a37" data-indicator-mode="none" data-tooltip-global="You have unread notifications" data-tooltip-unavailable="Notifications are unavailable at the moment." data-tooltip-none="You have no unread notifications" data-fetch-indicator-src="/notifications/indicator" data-fetch-indicator-enabled="true" data-view-component="true" class="js-socket-channel" data-fetch-retry-delay-time="500" data-catalyst="">
  <a id="AppHeader-notifications-button" href="/notifications" class="Header-link notification-indicator position-relative tooltipped tooltipped-sw" data-hotkey="g n" data-target="notification-indicator.link" aria-label="You have no unread notifications" data-analytics-event="{&quot;category&quot;:&quot;Header&quot;,&quot;action&quot;:&quot;go to notifications&quot;,&quot;label&quot;:&quot;icon:read&quot;}">

    <span data-target="notification-indicator.badge" class="mail-status unread" hidden="">
    </span>

      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-bell">
    <path d="M8 16a2 2 0 0 0 1.985-1.75c.017-.137-.097-.25-.235-.25h-3.5c-.138 0-.252.113-.235.25A2 2 0 0 0 8 16ZM3 5a5 5 0 0 1 10 0v2.947c0 .05.015.098.042.139l1.703 2.555A1.519 1.519 0 0 1 13.482 13H2.518a1.516 1.516 0 0 1-1.263-2.36l1.703-2.554A.255.255 0 0 0 3 7.947Zm5-3.5A3.5 3.5 0 0 0 4.5 5v2.947c0 .346-.102.683-.294.97l-1.703 2.556a.017.017 0 0 0-.003.01l.001.006c0 .002.002.004.004.006l.006.004.007.001h10.964l.007-.001.006-.004.004-.006.001-.007a.017.017 0 0 0-.003-.01l-1.703-2.554a1.745 1.745 0 0 1-.294-.97V5A3.5 3.5 0 0 0 8 1.5Z"></path>
</svg>
  </a>

</notification-indicator>
    </div>


    <div class="Header-item position-relative d-none d-md-flex">
        <details class="details-overlay details-reset">
  <summary class="Header-link" aria-label="Create new…" data-analytics-event="{&quot;category&quot;:&quot;Header&quot;,&quot;action&quot;:&quot;create new&quot;,&quot;label&quot;:&quot;icon:add&quot;}" aria-haspopup="menu" role="button">
    <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-plus">
    <path d="M7.75 2a.75.75 0 0 1 .75.75V7h4.25a.75.75 0 0 1 0 1.5H8.5v4.25a.75.75 0 0 1-1.5 0V8.5H2.75a.75.75 0 0 1 0-1.5H7V2.75A.75.75 0 0 1 7.75 2Z"></path>
</svg> <span class="dropdown-caret"></span>
  </summary>
  <details-menu class="dropdown-menu dropdown-menu-sw" role="menu" data-focus-trap="suspended"><span class="sentinel" tabindex="0" aria-hidden="true"></span>
    
<a role="menuitem" class="dropdown-item" href="/new" data-ga-click="Header, create new repository">
  New repository
</a>

  <a role="menuitem" class="dropdown-item" href="/new/import" data-ga-click="Header, import a repository">
    Import repository
  </a>

  <a role="menuitem" class="dropdown-item" href="/codespaces/new">
    New codespace
  </a>

<a role="menuitem" class="dropdown-item" href="https://gist.github.com/" data-ga-click="Header, create new gist">
  New gist
</a>

  <a role="menuitem" class="dropdown-item" href="/organizations/new" data-ga-click="Header, create new organization">
    New organization
  </a>



  <span class="sentinel" tabindex="0" aria-hidden="true"></span></details-menu>
</details>

    </div>

    <div class="Header-item position-relative mr-0 d-none d-md-flex">
        
  <details class="details-overlay details-reset js-feature-preview-indicator-container" data-feature-preview-indicator-src="/users/S230306/feature_preview/indicator_check">

  <summary class="Header-link" aria-label="View profile and more" data-analytics-event="{&quot;category&quot;:&quot;Header&quot;,&quot;action&quot;:&quot;show menu&quot;,&quot;label&quot;:&quot;icon:avatar&quot;}" aria-haspopup="menu" role="button">
    <img src="https://avatars.githubusercontent.com/u/99464989?s=40&amp;v=4" alt="@S230306" size="20" height="20" width="20" data-view-component="true" class="avatar avatar-small circle">
      <span class="unread-indicator js-feature-preview-indicator" style="top: 1px;" hidden=""></span>
    <span class="dropdown-caret"></span>
  </summary>
  <details-menu class="dropdown-menu dropdown-menu-sw" style="width: 180px" preload="" role="menu" data-focus-trap="suspended"><span class="sentinel" tabindex="0" aria-hidden="true"></span>
      <include-fragment src="/users/99464989/menu" loading="lazy">
        <p class="text-center mt-3" data-hide-on-error="">
          <svg style="box-sizing: content-box; color: var(--color-icon-primary);" width="32" height="32" viewBox="0 0 16 16" fill="none" data-view-component="true" class="anim-rotate">
  <circle cx="8" cy="8" r="7" stroke="currentColor" stroke-opacity="0.25" stroke-width="2" vector-effect="non-scaling-stroke"></circle>
  <path d="M15 8a7.002 7.002 0 00-7-7" stroke="currentColor" stroke-width="2" stroke-linecap="round" vector-effect="non-scaling-stroke"></path>
</svg>
        </p>
        <p class="ml-1 mb-2 mt-2 color-fg-default" data-show-on-error="">
          <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-alert">
    <path d="M6.457 1.047c.659-1.234 2.427-1.234 3.086 0l6.082 11.378A1.75 1.75 0 0 1 14.082 15H1.918a1.75 1.75 0 0 1-1.543-2.575Zm1.763.707a.25.25 0 0 0-.44 0L1.698 13.132a.25.25 0 0 0 .22.368h12.164a.25.25 0 0 0 .22-.368Zm.53 3.996v2.5a.75.75 0 0 1-1.5 0v-2.5a.75.75 0 0 1 1.5 0ZM9 11a1 1 0 1 1-2 0 1 1 0 0 1 2 0Z"></path>
</svg>
          Sorry, something went wrong.
        </p>
      </include-fragment>
  <span class="sentinel" tabindex="0" aria-hidden="true"></span></details-menu>
</details>

    </div>
</header>

          
    </div>

  <div id="start-of-content" class="show-on-focus"></div>







    <div id="js-flash-container" data-turbo-replace="">





  <template class="js-flash-template">
    
<div class="flash flash-full   {{ className }}">
  <div class="px-2">
    <button autofocus="" class="flash-close js-flash-close" type="button" aria-label="Dismiss this message">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-x">
    <path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path>
</svg>
    </button>
    <div aria-atomic="true" role="alert" class="js-flash-alert">
      
      <div>{{ message }}</div>

    </div>
  </div>
</div>
  </template>
</div>


    
    <notification-shelf-watcher data-base-url="https://github.com/notifications/beta/shelf" data-channel="eyJjIjoibm90aWZpY2F0aW9uLWNoYW5nZWQ6OTk0NjQ5ODkiLCJ0IjoxNjgzMTA5OTI2fQ==--24b89ae96e98da2581d4d0eacf63a027d908d712c2c489cf35ccaad056603a37" data-view-component="true" class="js-socket-channel" data-refresh-delay="500" data-catalyst=""></notification-shelf-watcher>
  <div hidden="" data-initial="" data-target="notification-shelf-watcher.placeholder"></div>






      <details class="details-reset details-overlay details-overlay-dark js-command-palette-dialog" id="command-palette-pjax-container" data-turbo-replace="">
  <summary aria-label="command palette trigger" tabindex="-1" role="button"></summary>
  <details-dialog class="command-palette-details-dialog d-flex flex-column flex-justify-center height-fit" aria-label="command palette" role="dialog" aria-modal="true">
    <command-palette class="command-palette color-bg-default rounded-3 border color-shadow-small" return-to="/bbottema/simple-java-mail/blob/master/README.md" user-id="99464989" activation-hotkey="Mod+k,Mod+Alt+k" command-mode-hotkey="Mod+Shift+k" data-action="
        command-palette-input-ready:command-palette#inputReady
        command-palette-page-stack-updated:command-palette#updateInputScope
        itemsUpdated:command-palette#itemsUpdated
        keydown:command-palette#onKeydown
        loadingStateChanged:command-palette#loadingStateChanged
        selectedItemChanged:command-palette#selectedItemChanged
        pageFetchError:command-palette#pageFetchError
      " data-catalyst="">

        <command-palette-mode data-char="#" data-scope-types="[&quot;&quot;]" data-placeholder="Search issues and pull requests" data-catalyst=""></command-palette-mode>
        <command-palette-mode data-char="#" data-scope-types="[&quot;owner&quot;,&quot;repository&quot;]" data-placeholder="Search issues, pull requests, discussions, and projects" data-catalyst=""></command-palette-mode>
        <command-palette-mode data-char="!" data-scope-types="[&quot;owner&quot;,&quot;repository&quot;]" data-placeholder="Search projects" data-catalyst=""></command-palette-mode>
        <command-palette-mode data-char="@" data-scope-types="[&quot;&quot;]" data-placeholder="Search or jump to a user, organization, or repository" data-catalyst=""></command-palette-mode>
        <command-palette-mode data-char="@" data-scope-types="[&quot;owner&quot;]" data-placeholder="Search or jump to a repository" data-catalyst=""></command-palette-mode>
        <command-palette-mode data-char="/" data-scope-types="[&quot;repository&quot;]" data-placeholder="Search files" data-catalyst=""></command-palette-mode>
        <command-palette-mode data-char="?" data-placeholder="" data-catalyst="" data-scope-types=""></command-palette-mode>
        <command-palette-mode data-char=">" data-placeholder="Run a command" data-scope-types="" data-catalyst=""></command-palette-mode>
        <command-palette-mode data-char="" data-scope-types="[&quot;&quot;]" data-placeholder="Search or jump to..." data-catalyst=""></command-palette-mode>
        <command-palette-mode data-char="" data-scope-types="[&quot;owner&quot;]" data-placeholder="Search or jump to..." data-catalyst=""></command-palette-mode>
      <command-palette-mode class="js-command-palette-default-mode" data-char="" data-placeholder="Search or jump to..." data-scope-types="" data-catalyst=""></command-palette-mode>

      <command-palette-input placeholder="Search or jump to..." data-action="
          command-palette-input:command-palette#onInput
          command-palette-select:command-palette#onSelect
          command-palette-descope:command-palette#onDescope
          command-palette-cleared:command-palette#onInputClear
        " data-catalyst="" class="d-flex flex-items-center flex-nowrap py-1 pl-3 pr-2 border-bottom">
        <div class="js-search-icon d-flex flex-items-center mr-2" style="height: 26px">
          <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-search color-fg-muted">
    <path d="M10.68 11.74a6 6 0 0 1-7.922-8.982 6 6 0 0 1 8.982 7.922l3.04 3.04a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215ZM11.5 7a4.499 4.499 0 1 0-8.997 0A4.499 4.499 0 0 0 11.5 7Z"></path>
</svg>
        </div>
        <div class="js-spinner d-flex flex-items-center mr-2 color-fg-muted" hidden="">
          <svg aria-label="Loading" class="anim-rotate" viewBox="0 0 16 16" fill="none" width="16" height="16">
            <circle cx="8" cy="8" r="7" stroke="currentColor" stroke-opacity="0.25" stroke-width="2" vector-effect="non-scaling-stroke"></circle>
            <path d="M15 8a7.002 7.002 0 00-7-7" stroke="currentColor" stroke-width="2" stroke-linecap="round" vector-effect="non-scaling-stroke"></path>
          </svg>
        </div>
        <command-palette-scope data-catalyst="" class="d-inline-flex">
          <div data-target="command-palette-scope.placeholder" hidden="" class="color-fg-subtle">/&nbsp;&nbsp;<span class="text-semibold color-fg-default">...</span>&nbsp;&nbsp;/&nbsp;&nbsp;</div>
              <command-palette-token data-text="bbottema" data-id="MDQ6VXNlcjIxMTU3MTg=" data-type="owner" data-value="bbottema" data-targets="command-palette-scope.tokens" class="color-fg-default text-semibold" style="white-space:nowrap;line-height:20px;" id="" data-catalyst="">bbottema<span class="color-fg-subtle text-normal">&nbsp;&nbsp;/&nbsp;&nbsp;</span></command-palette-token>
              <command-palette-token data-text="simple-java-mail" data-id="MDEwOlJlcG9zaXRvcnkzNDEwMDQ0MQ==" data-type="repository" data-value="simple-java-mail" data-targets="command-palette-scope.tokens" class="color-fg-default text-semibold" style="white-space:nowrap;line-height:20px;" id="" data-catalyst="">simple-java-mail<span class="color-fg-subtle text-normal">&nbsp;&nbsp;/&nbsp;&nbsp;</span></command-palette-token>
        </command-palette-scope>
        <div class="command-palette-input-group flex-1 form-control border-0 box-shadow-none" style="z-index: 0">
          <div class="command-palette-typeahead position-absolute d-flex flex-items-center Truncate">
            <span class="typeahead-segment input-mirror" data-target="command-palette-input.mirror"></span>
            <span class="Truncate-text" data-target="command-palette-input.typeaheadText"></span>
            <span class="typeahead-segment" data-target="command-palette-input.typeaheadPlaceholder"></span>
          </div>
          <input class="js-overlay-input typeahead-input d-none" disabled="" tabindex="-1" aria-label="Hidden input for typeahead">
          <input type="text" autocomplete="off" autocorrect="off" autocapitalize="off" spellcheck="false" class="js-input typeahead-input form-control border-0 box-shadow-none input-block width-full no-focus-indicator" aria-label="Command palette input" aria-haspopup="listbox" aria-expanded="false" aria-autocomplete="list" aria-controls="command-palette-page-stack" role="combobox" data-action="
              input:command-palette-input#onInput
              keydown:command-palette-input#onKeydown
            " placeholder="Search or jump to...">
        </div>
          <div data-view-component="true" class="position-relative d-inline-block">
    <button aria-keyshortcuts="Control+Backspace" data-action="click:command-palette-input#onClear keypress:command-palette-input#onClear" data-target="command-palette-input.clearButton" id="command-palette-clear-button" hidden="hidden" type="button" data-view-component="true" class="btn-octicon command-palette-input-clear-button" aria-labelledby="tooltip-4d05a2dc-a571-481b-a632-38cf09399f1b">      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-x-circle-fill">
    <path d="M2.343 13.657A8 8 0 1 1 13.658 2.343 8 8 0 0 1 2.343 13.657ZM6.03 4.97a.751.751 0 0 0-1.042.018.751.751 0 0 0-.018 1.042L6.94 8 4.97 9.97a.749.749 0 0 0 .326 1.275.749.749 0 0 0 .734-.215L8 9.06l1.97 1.97a.749.749 0 0 0 1.275-.326.749.749 0 0 0-.215-.734L9.06 8l1.97-1.97a.749.749 0 0 0-.326-1.275.749.749 0 0 0-.734.215L8 6.94Z"></path>
</svg>
</button>    <tool-tip id="tooltip-4d05a2dc-a571-481b-a632-38cf09399f1b" for="command-palette-clear-button" data-direction="w" data-type="label" data-view-component="true" class="sr-only position-absolute" aria-hidden="true" role="tooltip">Clear Command Palette</tool-tip>
</div>
      </command-palette-input>

      <command-palette-page-stack data-default-scope-id="MDEwOlJlcG9zaXRvcnkzNDEwMDQ0MQ==" data-default-scope-type="Repository" data-action="command-palette-page-octicons-cached:command-palette-page-stack#cacheOcticons" data-current-mode="" data-catalyst="" data-target="command-palette.pageStack" data-current-query-text="">
          <command-palette-tip class="color-fg-muted f6 px-3 py-1 my-2" data-scope-types="[&quot;&quot;,&quot;owner&quot;,&quot;repository&quot;]" data-mode="" data-value="" data-match-mode="" data-catalyst="" hidden="">
            <div class="d-flex flex-items-start flex-justify-between">
              <div>
                <span class="text-bold">Tip:</span>
                  Type <kbd class="hx_kbd">#</kbd> to search pull requests
              </div>
              <div class="ml-2 flex-shrink-0">
                Type <kbd class="hx_kbd">?</kbd> for help and tips
              </div>
            </div>
          </command-palette-tip>
          <command-palette-tip class="color-fg-muted f6 px-3 py-1 my-2" data-scope-types="[&quot;&quot;,&quot;owner&quot;,&quot;repository&quot;]" data-mode="" data-value="" data-match-mode="" data-catalyst="" hidden="">
            <div class="d-flex flex-items-start flex-justify-between">
              <div>
                <span class="text-bold">Tip:</span>
                  Type <kbd class="hx_kbd">#</kbd> to search issues
              </div>
              <div class="ml-2 flex-shrink-0">
                Type <kbd class="hx_kbd">?</kbd> for help and tips
              </div>
            </div>
          </command-palette-tip>
          <command-palette-tip class="color-fg-muted f6 px-3 py-1 my-2" data-scope-types="[&quot;owner&quot;,&quot;repository&quot;]" data-mode="" data-value="" data-match-mode="" data-catalyst="" hidden="">
            <div class="d-flex flex-items-start flex-justify-between">
              <div>
                <span class="text-bold">Tip:</span>
                  Type <kbd class="hx_kbd">#</kbd> to search discussions
              </div>
              <div class="ml-2 flex-shrink-0">
                Type <kbd class="hx_kbd">?</kbd> for help and tips
              </div>
            </div>
          </command-palette-tip>
          <command-palette-tip class="color-fg-muted f6 px-3 py-1 my-2" data-scope-types="[&quot;owner&quot;,&quot;repository&quot;]" data-mode="" data-value="" data-match-mode="" data-catalyst="" hidden="">
            <div class="d-flex flex-items-start flex-justify-between">
              <div>
                <span class="text-bold">Tip:</span>
                  Type <kbd class="hx_kbd">!</kbd> to search projects
              </div>
              <div class="ml-2 flex-shrink-0">
                Type <kbd class="hx_kbd">?</kbd> for help and tips
              </div>
            </div>
          </command-palette-tip>
          <command-palette-tip class="color-fg-muted f6 px-3 py-1 my-2" data-scope-types="[&quot;owner&quot;]" data-mode="" data-value="" data-match-mode="" data-catalyst="" hidden="">
            <div class="d-flex flex-items-start flex-justify-between">
              <div>
                <span class="text-bold">Tip:</span>
                  Type <kbd class="hx_kbd">@</kbd> to search teams
              </div>
              <div class="ml-2 flex-shrink-0">
                Type <kbd class="hx_kbd">?</kbd> for help and tips
              </div>
            </div>
          </command-palette-tip>
          <command-palette-tip class="color-fg-muted f6 px-3 py-1 my-2" data-scope-types="[&quot;&quot;]" data-mode="" data-value="" data-match-mode="" data-catalyst="" hidden="">
            <div class="d-flex flex-items-start flex-justify-between">
              <div>
                <span class="text-bold">Tip:</span>
                  Type <kbd class="hx_kbd">@</kbd> to search people and organizations
              </div>
              <div class="ml-2 flex-shrink-0">
                Type <kbd class="hx_kbd">?</kbd> for help and tips
              </div>
            </div>
          </command-palette-tip>
          <command-palette-tip class="color-fg-muted f6 px-3 py-1 my-2" data-scope-types="[&quot;&quot;,&quot;owner&quot;,&quot;repository&quot;]" data-mode="" data-value="" data-match-mode="" data-catalyst="" hidden="">
            <div class="d-flex flex-items-start flex-justify-between">
              <div>
                <span class="text-bold">Tip:</span>
                  Type <kbd class="hx_kbd">&gt;</kbd> to activate command mode
              </div>
              <div class="ml-2 flex-shrink-0">
                Type <kbd class="hx_kbd">?</kbd> for help and tips
              </div>
            </div>
          </command-palette-tip>
          <command-palette-tip class="color-fg-muted f6 px-3 py-1 my-2" data-scope-types="[&quot;&quot;,&quot;owner&quot;,&quot;repository&quot;]" data-mode="" data-value="" data-match-mode="" data-catalyst="" hidden="">
            <div class="d-flex flex-items-start flex-justify-between">
              <div>
                <span class="text-bold">Tip:</span>
                  Go to your accessibility settings to change your keyboard shortcuts
              </div>
              <div class="ml-2 flex-shrink-0">
                Type <kbd class="hx_kbd">?</kbd> for help and tips
              </div>
            </div>
          </command-palette-tip>
          <command-palette-tip class="color-fg-muted f6 px-3 py-1 my-2" data-scope-types="[&quot;&quot;,&quot;owner&quot;,&quot;repository&quot;]" data-mode="#" data-value="" data-match-mode="" data-catalyst="" hidden="">
            <div class="d-flex flex-items-start flex-justify-between">
              <div>
                <span class="text-bold">Tip:</span>
                  Type author:@me to search your content
              </div>
              <div class="ml-2 flex-shrink-0">
                Type <kbd class="hx_kbd">?</kbd> for help and tips
              </div>
            </div>
          </command-palette-tip>
          <command-palette-tip class="color-fg-muted f6 px-3 py-1 my-2" data-scope-types="[&quot;&quot;,&quot;owner&quot;,&quot;repository&quot;]" data-mode="#" data-value="" data-match-mode="" data-catalyst="" hidden="">
            <div class="d-flex flex-items-start flex-justify-between">
              <div>
                <span class="text-bold">Tip:</span>
                  Type is:pr to filter to pull requests
              </div>
              <div class="ml-2 flex-shrink-0">
                Type <kbd class="hx_kbd">?</kbd> for help and tips
              </div>
            </div>
          </command-palette-tip>
          <command-palette-tip class="color-fg-muted f6 px-3 py-1 my-2" data-scope-types="[&quot;&quot;,&quot;owner&quot;,&quot;repository&quot;]" data-mode="#" data-value="" data-match-mode="" data-catalyst="" hidden="">
            <div class="d-flex flex-items-start flex-justify-between">
              <div>
                <span class="text-bold">Tip:</span>
                  Type is:issue to filter to issues
              </div>
              <div class="ml-2 flex-shrink-0">
                Type <kbd class="hx_kbd">?</kbd> for help and tips
              </div>
            </div>
          </command-palette-tip>
          <command-palette-tip class="color-fg-muted f6 px-3 py-1 my-2" data-scope-types="[&quot;owner&quot;,&quot;repository&quot;]" data-mode="#" data-value="" data-match-mode="" data-catalyst="" hidden="">
            <div class="d-flex flex-items-start flex-justify-between">
              <div>
                <span class="text-bold">Tip:</span>
                  Type is:project to filter to projects
              </div>
              <div class="ml-2 flex-shrink-0">
                Type <kbd class="hx_kbd">?</kbd> for help and tips
              </div>
            </div>
          </command-palette-tip>
          <command-palette-tip class="color-fg-muted f6 px-3 py-1 my-2" data-scope-types="[&quot;&quot;,&quot;owner&quot;,&quot;repository&quot;]" data-mode="#" data-value="" data-match-mode="" data-catalyst="" hidden="">
            <div class="d-flex flex-items-start flex-justify-between">
              <div>
                <span class="text-bold">Tip:</span>
                  Type is:open to filter to open content
              </div>
              <div class="ml-2 flex-shrink-0">
                Type <kbd class="hx_kbd">?</kbd> for help and tips
              </div>
            </div>
          </command-palette-tip>
        <command-palette-tip class="mx-3 my-2 flash flash-error d-flex flex-items-center" data-scope-types="*" data-on-error="" data-mode="*" data-catalyst="" hidden="" data-match-mode="" data-value="*">
          <div>
            <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-alert">
    <path d="M6.457 1.047c.659-1.234 2.427-1.234 3.086 0l6.082 11.378A1.75 1.75 0 0 1 14.082 15H1.918a1.75 1.75 0 0 1-1.543-2.575Zm1.763.707a.25.25 0 0 0-.44 0L1.698 13.132a.25.25 0 0 0 .22.368h12.164a.25.25 0 0 0 .22-.368Zm.53 3.996v2.5a.75.75 0 0 1-1.5 0v-2.5a.75.75 0 0 1 1.5 0ZM9 11a1 1 0 1 1-2 0 1 1 0 0 1 2 0Z"></path>
</svg>
          </div>
          <div class="px-2">
            We’ve encountered an error and some results aren't available at this time. Type a new search or try again later.
          </div>
        </command-palette-tip>
        <command-palette-tip class="h4 color-fg-default pl-3 pb-2 pt-3" data-on-empty="" data-scope-types="*" data-match-mode="[^?]|^$" data-mode="*" data-catalyst="" hidden="" data-value="*">
          No results matched your search
        </command-palette-tip>

        <div hidden="">

            <div data-targets="command-palette-page-stack.localOcticons" data-octicon-id="arrow-right-color-fg-muted">
              <svg height="16" class="octicon octicon-arrow-right color-fg-muted" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path d="M8.22 2.97a.75.75 0 0 1 1.06 0l4.25 4.25a.75.75 0 0 1 0 1.06l-4.25 4.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042l2.97-2.97H3.75a.75.75 0 0 1 0-1.5h7.44L8.22 4.03a.75.75 0 0 1 0-1.06Z"></path></svg>
            </div>
            <div data-targets="command-palette-page-stack.localOcticons" data-octicon-id="arrow-right-color-fg-default">
              <svg height="16" class="octicon octicon-arrow-right color-fg-default" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path d="M8.22 2.97a.75.75 0 0 1 1.06 0l4.25 4.25a.75.75 0 0 1 0 1.06l-4.25 4.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042l2.97-2.97H3.75a.75.75 0 0 1 0-1.5h7.44L8.22 4.03a.75.75 0 0 1 0-1.06Z"></path></svg>
            </div>
            <div data-targets="command-palette-page-stack.localOcticons" data-octicon-id="codespaces-color-fg-muted">
              <svg height="16" class="octicon octicon-codespaces color-fg-muted" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path d="M0 11.25c0-.966.784-1.75 1.75-1.75h12.5c.966 0 1.75.784 1.75 1.75v3A1.75 1.75 0 0 1 14.25 16H1.75A1.75 1.75 0 0 1 0 14.25Zm2-9.5C2 .784 2.784 0 3.75 0h8.5C13.216 0 14 .784 14 1.75v5a1.75 1.75 0 0 1-1.75 1.75h-8.5A1.75 1.75 0 0 1 2 6.75Zm1.75-.25a.25.25 0 0 0-.25.25v5c0 .138.112.25.25.25h8.5a.25.25 0 0 0 .25-.25v-5a.25.25 0 0 0-.25-.25Zm-2 9.5a.25.25 0 0 0-.25.25v3c0 .138.112.25.25.25h12.5a.25.25 0 0 0 .25-.25v-3a.25.25 0 0 0-.25-.25Z"></path><path d="M7 12.75a.75.75 0 0 1 .75-.75h4.5a.75.75 0 0 1 0 1.5h-4.5a.75.75 0 0 1-.75-.75Zm-4 0a.75.75 0 0 1 .75-.75h.5a.75.75 0 0 1 0 1.5h-.5a.75.75 0 0 1-.75-.75Z"></path></svg>
            </div>
            <div data-targets="command-palette-page-stack.localOcticons" data-octicon-id="copy-color-fg-muted">
              <svg height="16" class="octicon octicon-copy color-fg-muted" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path></svg>
            </div>
            <div data-targets="command-palette-page-stack.localOcticons" data-octicon-id="dash-color-fg-muted">
              <svg height="16" class="octicon octicon-dash color-fg-muted" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path d="M2 7.75A.75.75 0 0 1 2.75 7h10a.75.75 0 0 1 0 1.5h-10A.75.75 0 0 1 2 7.75Z"></path></svg>
            </div>
            <div data-targets="command-palette-page-stack.localOcticons" data-octicon-id="file-color-fg-muted">
              <svg height="16" class="octicon octicon-file color-fg-muted" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path d="M2 1.75C2 .784 2.784 0 3.75 0h6.586c.464 0 .909.184 1.237.513l2.914 2.914c.329.328.513.773.513 1.237v9.586A1.75 1.75 0 0 1 13.25 16h-9.5A1.75 1.75 0 0 1 2 14.25Zm1.75-.25a.25.25 0 0 0-.25.25v12.5c0 .138.112.25.25.25h9.5a.25.25 0 0 0 .25-.25V6h-2.75A1.75 1.75 0 0 1 9 4.25V1.5Zm6.75.062V4.25c0 .138.112.25.25.25h2.688l-.011-.013-2.914-2.914-.013-.011Z"></path></svg>
            </div>
            <div data-targets="command-palette-page-stack.localOcticons" data-octicon-id="gear-color-fg-muted">
              <svg height="16" class="octicon octicon-gear color-fg-muted" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path d="M8 0a8.2 8.2 0 0 1 .701.031C9.444.095 9.99.645 10.16 1.29l.288 1.107c.018.066.079.158.212.224.231.114.454.243.668.386.123.082.233.09.299.071l1.103-.303c.644-.176 1.392.021 1.82.63.27.385.506.792.704 1.218.315.675.111 1.422-.364 1.891l-.814.806c-.049.048-.098.147-.088.294.016.257.016.515 0 .772-.01.147.038.246.088.294l.814.806c.475.469.679 1.216.364 1.891a7.977 7.977 0 0 1-.704 1.217c-.428.61-1.176.807-1.82.63l-1.102-.302c-.067-.019-.177-.011-.3.071a5.909 5.909 0 0 1-.668.386c-.133.066-.194.158-.211.224l-.29 1.106c-.168.646-.715 1.196-1.458 1.26a8.006 8.006 0 0 1-1.402 0c-.743-.064-1.289-.614-1.458-1.26l-.289-1.106c-.018-.066-.079-.158-.212-.224a5.738 5.738 0 0 1-.668-.386c-.123-.082-.233-.09-.299-.071l-1.103.303c-.644.176-1.392-.021-1.82-.63a8.12 8.12 0 0 1-.704-1.218c-.315-.675-.111-1.422.363-1.891l.815-.806c.05-.048.098-.147.088-.294a6.214 6.214 0 0 1 0-.772c.01-.147-.038-.246-.088-.294l-.815-.806C.635 6.045.431 5.298.746 4.623a7.92 7.92 0 0 1 .704-1.217c.428-.61 1.176-.807 1.82-.63l1.102.302c.067.019.177.011.3-.071.214-.143.437-.272.668-.386.133-.066.194-.158.211-.224l.29-1.106C6.009.645 6.556.095 7.299.03 7.53.01 7.764 0 8 0Zm-.571 1.525c-.036.003-.108.036-.137.146l-.289 1.105c-.147.561-.549.967-.998 1.189-.173.086-.34.183-.5.29-.417.278-.97.423-1.529.27l-1.103-.303c-.109-.03-.175.016-.195.045-.22.312-.412.644-.573.99-.014.031-.021.11.059.19l.815.806c.411.406.562.957.53 1.456a4.709 4.709 0 0 0 0 .582c.032.499-.119 1.05-.53 1.456l-.815.806c-.081.08-.073.159-.059.19.162.346.353.677.573.989.02.03.085.076.195.046l1.102-.303c.56-.153 1.113-.008 1.53.27.161.107.328.204.501.29.447.222.85.629.997 1.189l.289 1.105c.029.109.101.143.137.146a6.6 6.6 0 0 0 1.142 0c.036-.003.108-.036.137-.146l.289-1.105c.147-.561.549-.967.998-1.189.173-.086.34-.183.5-.29.417-.278.97-.423 1.529-.27l1.103.303c.109.029.175-.016.195-.045.22-.313.411-.644.573-.99.014-.031.021-.11-.059-.19l-.815-.806c-.411-.406-.562-.957-.53-1.456a4.709 4.709 0 0 0 0-.582c-.032-.499.119-1.05.53-1.456l.815-.806c.081-.08.073-.159.059-.19a6.464 6.464 0 0 0-.573-.989c-.02-.03-.085-.076-.195-.046l-1.102.303c-.56.153-1.113.008-1.53-.27a4.44 4.44 0 0 0-.501-.29c-.447-.222-.85-.629-.997-1.189l-.289-1.105c-.029-.11-.101-.143-.137-.146a6.6 6.6 0 0 0-1.142 0ZM11 8a3 3 0 1 1-6 0 3 3 0 0 1 6 0ZM9.5 8a1.5 1.5 0 1 0-3.001.001A1.5 1.5 0 0 0 9.5 8Z"></path></svg>
            </div>
            <div data-targets="command-palette-page-stack.localOcticons" data-octicon-id="lock-color-fg-muted">
              <svg height="16" class="octicon octicon-lock color-fg-muted" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path d="M4 4a4 4 0 0 1 8 0v2h.25c.966 0 1.75.784 1.75 1.75v5.5A1.75 1.75 0 0 1 12.25 15h-8.5A1.75 1.75 0 0 1 2 13.25v-5.5C2 6.784 2.784 6 3.75 6H4Zm8.25 3.5h-8.5a.25.25 0 0 0-.25.25v5.5c0 .138.112.25.25.25h8.5a.25.25 0 0 0 .25-.25v-5.5a.25.25 0 0 0-.25-.25ZM10.5 6V4a2.5 2.5 0 1 0-5 0v2Z"></path></svg>
            </div>
            <div data-targets="command-palette-page-stack.localOcticons" data-octicon-id="moon-color-fg-muted">
              <svg height="16" class="octicon octicon-moon color-fg-muted" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path d="M9.598 1.591a.749.749 0 0 1 .785-.175 7.001 7.001 0 1 1-8.967 8.967.75.75 0 0 1 .961-.96 5.5 5.5 0 0 0 7.046-7.046.75.75 0 0 1 .175-.786Zm1.616 1.945a7 7 0 0 1-7.678 7.678 5.499 5.499 0 1 0 7.678-7.678Z"></path></svg>
            </div>
            <div data-targets="command-palette-page-stack.localOcticons" data-octicon-id="person-color-fg-muted">
              <svg height="16" class="octicon octicon-person color-fg-muted" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path d="M10.561 8.073a6.005 6.005 0 0 1 3.432 5.142.75.75 0 1 1-1.498.07 4.5 4.5 0 0 0-8.99 0 .75.75 0 0 1-1.498-.07 6.004 6.004 0 0 1 3.431-5.142 3.999 3.999 0 1 1 5.123 0ZM10.5 5a2.5 2.5 0 1 0-5 0 2.5 2.5 0 0 0 5 0Z"></path></svg>
            </div>
            <div data-targets="command-palette-page-stack.localOcticons" data-octicon-id="pencil-color-fg-muted">
              <svg height="16" class="octicon octicon-pencil color-fg-muted" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path d="M11.013 1.427a1.75 1.75 0 0 1 2.474 0l1.086 1.086a1.75 1.75 0 0 1 0 2.474l-8.61 8.61c-.21.21-.47.364-.756.445l-3.251.93a.75.75 0 0 1-.927-.928l.929-3.25c.081-.286.235-.547.445-.758l8.61-8.61Zm.176 4.823L9.75 4.81l-6.286 6.287a.253.253 0 0 0-.064.108l-.558 1.953 1.953-.558a.253.253 0 0 0 .108-.064Zm1.238-3.763a.25.25 0 0 0-.354 0L10.811 3.75l1.439 1.44 1.263-1.263a.25.25 0 0 0 0-.354Z"></path></svg>
            </div>
            <div data-targets="command-palette-page-stack.localOcticons" data-octicon-id="issue-opened-open">
              <svg height="16" class="octicon octicon-issue-opened open" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path d="M8 9.5a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3Z"></path><path d="M8 0a8 8 0 1 1 0 16A8 8 0 0 1 8 0ZM1.5 8a6.5 6.5 0 1 0 13 0 6.5 6.5 0 0 0-13 0Z"></path></svg>
            </div>
            <div data-targets="command-palette-page-stack.localOcticons" data-octicon-id="git-pull-request-draft-color-fg-muted">
              <svg height="16" class="octicon octicon-git-pull-request-draft color-fg-muted" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path d="M3.25 1A2.25 2.25 0 0 1 4 5.372v5.256a2.251 2.251 0 1 1-1.5 0V5.372A2.251 2.251 0 0 1 3.25 1Zm9.5 14a2.25 2.25 0 1 1 0-4.5 2.25 2.25 0 0 1 0 4.5ZM2.5 3.25a.75.75 0 1 0 1.5 0 .75.75 0 0 0-1.5 0ZM3.25 12a.75.75 0 1 0 0 1.5.75.75 0 0 0 0-1.5Zm9.5 0a.75.75 0 1 0 0 1.5.75.75 0 0 0 0-1.5ZM14 7.5a1.25 1.25 0 1 1-2.5 0 1.25 1.25 0 0 1 2.5 0Zm0-4.25a1.25 1.25 0 1 1-2.5 0 1.25 1.25 0 0 1 2.5 0Z"></path></svg>
            </div>
            <div data-targets="command-palette-page-stack.localOcticons" data-octicon-id="search-color-fg-muted">
              <svg height="16" class="octicon octicon-search color-fg-muted" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path d="M10.68 11.74a6 6 0 0 1-7.922-8.982 6 6 0 0 1 8.982 7.922l3.04 3.04a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215ZM11.5 7a4.499 4.499 0 1 0-8.997 0A4.499 4.499 0 0 0 11.5 7Z"></path></svg>
            </div>
            <div data-targets="command-palette-page-stack.localOcticons" data-octicon-id="sun-color-fg-muted">
              <svg height="16" class="octicon octicon-sun color-fg-muted" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path d="M8 12a4 4 0 1 1 0-8 4 4 0 0 1 0 8Zm0-1.5a2.5 2.5 0 1 0 0-5 2.5 2.5 0 0 0 0 5Zm5.657-8.157a.75.75 0 0 1 0 1.061l-1.061 1.06a.749.749 0 0 1-1.275-.326.749.749 0 0 1 .215-.734l1.06-1.06a.75.75 0 0 1 1.06 0Zm-9.193 9.193a.75.75 0 0 1 0 1.06l-1.06 1.061a.75.75 0 1 1-1.061-1.06l1.06-1.061a.75.75 0 0 1 1.061 0ZM8 0a.75.75 0 0 1 .75.75v1.5a.75.75 0 0 1-1.5 0V.75A.75.75 0 0 1 8 0ZM3 8a.75.75 0 0 1-.75.75H.75a.75.75 0 0 1 0-1.5h1.5A.75.75 0 0 1 3 8Zm13 0a.75.75 0 0 1-.75.75h-1.5a.75.75 0 0 1 0-1.5h1.5A.75.75 0 0 1 16 8Zm-8 5a.75.75 0 0 1 .75.75v1.5a.75.75 0 0 1-1.5 0v-1.5A.75.75 0 0 1 8 13Zm3.536-1.464a.75.75 0 0 1 1.06 0l1.061 1.06a.75.75 0 0 1-1.06 1.061l-1.061-1.06a.75.75 0 0 1 0-1.061ZM2.343 2.343a.75.75 0 0 1 1.061 0l1.06 1.061a.751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018l-1.06-1.06a.75.75 0 0 1 0-1.06Z"></path></svg>
            </div>
            <div data-targets="command-palette-page-stack.localOcticons" data-octicon-id="sync-color-fg-muted">
              <svg height="16" class="octicon octicon-sync color-fg-muted" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path d="M1.705 8.005a.75.75 0 0 1 .834.656 5.5 5.5 0 0 0 9.592 2.97l-1.204-1.204a.25.25 0 0 1 .177-.427h3.646a.25.25 0 0 1 .25.25v3.646a.25.25 0 0 1-.427.177l-1.38-1.38A7.002 7.002 0 0 1 1.05 8.84a.75.75 0 0 1 .656-.834ZM8 2.5a5.487 5.487 0 0 0-4.131 1.869l1.204 1.204A.25.25 0 0 1 4.896 6H1.25A.25.25 0 0 1 1 5.75V2.104a.25.25 0 0 1 .427-.177l1.38 1.38A7.002 7.002 0 0 1 14.95 7.16a.75.75 0 0 1-1.49.178A5.5 5.5 0 0 0 8 2.5Z"></path></svg>
            </div>
            <div data-targets="command-palette-page-stack.localOcticons" data-octicon-id="trash-color-fg-muted">
              <svg height="16" class="octicon octicon-trash color-fg-muted" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path d="M11 1.75V3h2.25a.75.75 0 0 1 0 1.5H2.75a.75.75 0 0 1 0-1.5H5V1.75C5 .784 5.784 0 6.75 0h2.5C10.216 0 11 .784 11 1.75ZM4.496 6.675l.66 6.6a.25.25 0 0 0 .249.225h5.19a.25.25 0 0 0 .249-.225l.66-6.6a.75.75 0 0 1 1.492.149l-.66 6.6A1.748 1.748 0 0 1 10.595 15h-5.19a1.75 1.75 0 0 1-1.741-1.575l-.66-6.6a.75.75 0 1 1 1.492-.15ZM6.5 1.75V3h3V1.75a.25.25 0 0 0-.25-.25h-2.5a.25.25 0 0 0-.25.25Z"></path></svg>
            </div>
            <div data-targets="command-palette-page-stack.localOcticons" data-octicon-id="key-color-fg-muted">
              <svg height="16" class="octicon octicon-key color-fg-muted" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path d="M10.5 0a5.499 5.499 0 1 1-1.288 10.848l-.932.932a.749.749 0 0 1-.53.22H7v.75a.749.749 0 0 1-.22.53l-.5.5a.749.749 0 0 1-.53.22H5v.75a.749.749 0 0 1-.22.53l-.5.5a.749.749 0 0 1-.53.22h-2A1.75 1.75 0 0 1 0 14.25v-2c0-.199.079-.389.22-.53l4.932-4.932A5.5 5.5 0 0 1 10.5 0Zm-4 5.5c-.001.431.069.86.205 1.269a.75.75 0 0 1-.181.768L1.5 12.56v1.69c0 .138.112.25.25.25h1.69l.06-.06v-1.19a.75.75 0 0 1 .75-.75h1.19l.06-.06v-1.19a.75.75 0 0 1 .75-.75h1.19l1.023-1.025a.75.75 0 0 1 .768-.18A4 4 0 1 0 6.5 5.5ZM11 6a1 1 0 1 1 0-2 1 1 0 0 1 0 2Z"></path></svg>
            </div>
            <div data-targets="command-palette-page-stack.localOcticons" data-octicon-id="comment-discussion-color-fg-muted">
              <svg height="16" class="octicon octicon-comment-discussion color-fg-muted" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path d="M1.75 1h8.5c.966 0 1.75.784 1.75 1.75v5.5A1.75 1.75 0 0 1 10.25 10H7.061l-2.574 2.573A1.458 1.458 0 0 1 2 11.543V10h-.25A1.75 1.75 0 0 1 0 8.25v-5.5C0 1.784.784 1 1.75 1ZM1.5 2.75v5.5c0 .138.112.25.25.25h1a.75.75 0 0 1 .75.75v2.19l2.72-2.72a.749.749 0 0 1 .53-.22h3.5a.25.25 0 0 0 .25-.25v-5.5a.25.25 0 0 0-.25-.25h-8.5a.25.25 0 0 0-.25.25Zm13 2a.25.25 0 0 0-.25-.25h-.5a.75.75 0 0 1 0-1.5h.5c.966 0 1.75.784 1.75 1.75v5.5A1.75 1.75 0 0 1 14.25 12H14v1.543a1.458 1.458 0 0 1-2.487 1.03L9.22 12.28a.749.749 0 0 1 .326-1.275.749.749 0 0 1 .734.215l2.22 2.22v-2.19a.75.75 0 0 1 .75-.75h1a.25.25 0 0 0 .25-.25Z"></path></svg>
            </div>
            <div data-targets="command-palette-page-stack.localOcticons" data-octicon-id="bell-color-fg-muted">
              <svg height="16" class="octicon octicon-bell color-fg-muted" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path d="M8 16a2 2 0 0 0 1.985-1.75c.017-.137-.097-.25-.235-.25h-3.5c-.138 0-.252.113-.235.25A2 2 0 0 0 8 16ZM3 5a5 5 0 0 1 10 0v2.947c0 .05.015.098.042.139l1.703 2.555A1.519 1.519 0 0 1 13.482 13H2.518a1.516 1.516 0 0 1-1.263-2.36l1.703-2.554A.255.255 0 0 0 3 7.947Zm5-3.5A3.5 3.5 0 0 0 4.5 5v2.947c0 .346-.102.683-.294.97l-1.703 2.556a.017.017 0 0 0-.003.01l.001.006c0 .002.002.004.004.006l.006.004.007.001h10.964l.007-.001.006-.004.004-.006.001-.007a.017.017 0 0 0-.003-.01l-1.703-2.554a1.745 1.745 0 0 1-.294-.97V5A3.5 3.5 0 0 0 8 1.5Z"></path></svg>
            </div>
            <div data-targets="command-palette-page-stack.localOcticons" data-octicon-id="bell-slash-color-fg-muted">
              <svg height="16" class="octicon octicon-bell-slash color-fg-muted" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path d="m4.182 4.31.016.011 10.104 7.316.013.01 1.375.996a.75.75 0 1 1-.88 1.214L13.626 13H2.518a1.516 1.516 0 0 1-1.263-2.36l1.703-2.554A.255.255 0 0 0 3 7.947V5.305L.31 3.357a.75.75 0 1 1 .88-1.214Zm7.373 7.19L4.5 6.391v1.556c0 .346-.102.683-.294.97l-1.703 2.556a.017.017 0 0 0-.003.01c0 .005.002.009.005.012l.006.004.007.001ZM8 1.5c-.997 0-1.895.416-2.534 1.086A.75.75 0 1 1 4.38 1.55 5 5 0 0 1 13 5v2.373a.75.75 0 0 1-1.5 0V5A3.5 3.5 0 0 0 8 1.5ZM8 16a2 2 0 0 1-1.985-1.75c-.017-.137.097-.25.235-.25h3.5c.138 0 .252.113.235.25A2 2 0 0 1 8 16Z"></path></svg>
            </div>
            <div data-targets="command-palette-page-stack.localOcticons" data-octicon-id="paintbrush-color-fg-muted">
              <svg height="16" class="octicon octicon-paintbrush color-fg-muted" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path d="M11.134 1.535c.7-.509 1.416-.942 2.076-1.155.649-.21 1.463-.267 2.069.34.603.601.568 1.411.368 2.07-.202.668-.624 1.39-1.125 2.096-1.011 1.424-2.496 2.987-3.775 4.249-1.098 1.084-2.132 1.839-3.04 2.3a3.744 3.744 0 0 1-1.055 3.217c-.431.431-1.065.691-1.657.861-.614.177-1.294.287-1.914.357A21.151 21.151 0 0 1 .797 16H.743l.007-.75H.749L.742 16a.75.75 0 0 1-.743-.742l.743-.008-.742.007v-.054a21.25 21.25 0 0 1 .13-2.284c.067-.647.187-1.287.358-1.914.17-.591.43-1.226.86-1.657a3.746 3.746 0 0 1 3.227-1.054c.466-.893 1.225-1.907 2.314-2.982 1.271-1.255 2.833-2.75 4.245-3.777ZM1.62 13.089c-.051.464-.086.929-.104 1.395.466-.018.932-.053 1.396-.104a10.511 10.511 0 0 0 1.668-.309c.526-.151.856-.325 1.011-.48a2.25 2.25 0 1 0-3.182-3.182c-.155.155-.329.485-.48 1.01a10.515 10.515 0 0 0-.309 1.67Zm10.396-10.34c-1.224.89-2.605 2.189-3.822 3.384l1.718 1.718c1.21-1.205 2.51-2.597 3.387-3.833.47-.662.78-1.227.912-1.662.134-.444.032-.551.009-.575h-.001V1.78c-.014-.014-.113-.113-.548.027-.432.14-.995.462-1.655.942Zm-4.832 7.266-.001.001a9.859 9.859 0 0 0 1.63-1.142L7.155 7.216a9.7 9.7 0 0 0-1.161 1.607c.482.302.889.71 1.19 1.192Z"></path></svg>
            </div>

            <command-palette-item-group data-group-id="top" data-group-title="Top result" data-group-hint="" data-group-limits="{}" data-default-priority="0" data-catalyst="" class="py-2 border-top" hidden="true" data-skip-template="">
            
          <div class="d-flex flex-justify-between my-2 px-3">
            <span data-target="command-palette-item-group.header" class="color-fg-muted text-bold f6 text-normal">
              Top result
            </span>
            <span data-target="command-palette-item-group.header" class="color-fg-muted f6 text-normal">
              
            </span>
          </div>
          <div role="listbox" class="list-style-none" data-target="command-palette-item-group.list" aria-label="Top result results"></div>
        </command-palette-item-group>
            <command-palette-item-group data-group-id="commands" data-group-title="Commands" data-group-hint="Type > to filter" data-group-limits="{&quot;static_items_page&quot;:50,&quot;issue&quot;:50,&quot;pull_request&quot;:50,&quot;discussion&quot;:50}" data-default-priority="1" data-catalyst="" class="py-2 border-top" hidden="true" data-skip-template="">
            
          <div class="d-flex flex-justify-between my-2 px-3">
            <span data-target="command-palette-item-group.header" class="color-fg-muted text-bold f6 text-normal">
              Commands
            </span>
            <span data-target="command-palette-item-group.header" class="color-fg-muted f6 text-normal">
              Type &gt; to filter
            </span>
          </div>
          <div role="listbox" class="list-style-none" data-target="command-palette-item-group.list" aria-label="Commands results"></div>
        </command-palette-item-group>
            <command-palette-item-group data-group-id="global_commands" data-group-title="Global Commands" data-group-hint="Type > to filter" data-group-limits="{&quot;issue&quot;:0,&quot;pull_request&quot;:0,&quot;discussion&quot;:0}" data-default-priority="2" data-catalyst="" class="py-2 border-top" hidden="true" data-skip-template="">
            
          <div class="d-flex flex-justify-between my-2 px-3">
            <span data-target="command-palette-item-group.header" class="color-fg-muted text-bold f6 text-normal">
              Global Commands
            </span>
            <span data-target="command-palette-item-group.header" class="color-fg-muted f6 text-normal">
              Type &gt; to filter
            </span>
          </div>
          <div role="listbox" class="list-style-none" data-target="command-palette-item-group.list" aria-label="Global Commands results"></div>
        </command-palette-item-group>
            <command-palette-item-group data-group-id="this_page" data-group-title="This Page" data-group-hint="" data-group-limits="{}" data-default-priority="3" data-catalyst="" class="py-2 border-top" hidden="true" data-skip-template="">
            
          <div class="d-flex flex-justify-between my-2 px-3">
            <span data-target="command-palette-item-group.header" class="color-fg-muted text-bold f6 text-normal">
              This Page
            </span>
            <span data-target="command-palette-item-group.header" class="color-fg-muted f6 text-normal">
              
            </span>
          </div>
          <div role="listbox" class="list-style-none" data-target="command-palette-item-group.list" aria-label="This Page results"></div>
        </command-palette-item-group>
            <command-palette-item-group data-group-id="files" data-group-title="Files" data-group-hint="" data-group-limits="{}" data-default-priority="4" data-catalyst="" class="py-2 border-top" hidden="true" data-skip-template="">
            
          <div class="d-flex flex-justify-between my-2 px-3">
            <span data-target="command-palette-item-group.header" class="color-fg-muted text-bold f6 text-normal">
              Files
            </span>
            <span data-target="command-palette-item-group.header" class="color-fg-muted f6 text-normal">
              
            </span>
          </div>
          <div role="listbox" class="list-style-none" data-target="command-palette-item-group.list" aria-label="Files results"></div>
        </command-palette-item-group>
            <command-palette-item-group data-group-id="default" data-group-title="Default" data-group-hint="" data-group-limits="{&quot;static_items_page&quot;:50}" data-default-priority="5" data-catalyst="" class="py-2 border-top" hidden="true" data-skip-template="">
            
          <div role="listbox" class="list-style-none" data-target="command-palette-item-group.list" aria-label="Default results"></div>
        </command-palette-item-group>
            <command-palette-item-group data-group-id="pages" data-group-title="Pages" data-group-hint="" data-group-limits="{&quot;repository&quot;:10}" data-default-priority="6" data-catalyst="" class="py-2 border-top" hidden="true" data-skip-template="">
            
          <div class="d-flex flex-justify-between my-2 px-3">
            <span data-target="command-palette-item-group.header" class="color-fg-muted text-bold f6 text-normal">
              Pages
            </span>
            <span data-target="command-palette-item-group.header" class="color-fg-muted f6 text-normal">
              
            </span>
          </div>
          <div role="listbox" class="list-style-none" data-target="command-palette-item-group.list" aria-label="Pages results"></div>
        </command-palette-item-group>
            <command-palette-item-group data-group-id="access_policies" data-group-title="Access Policies" data-group-hint="" data-group-limits="{}" data-default-priority="7" data-catalyst="" class="py-2 border-top" hidden="true" data-skip-template="">
            
          <div class="d-flex flex-justify-between my-2 px-3">
            <span data-target="command-palette-item-group.header" class="color-fg-muted text-bold f6 text-normal">
              Access Policies
            </span>
            <span data-target="command-palette-item-group.header" class="color-fg-muted f6 text-normal">
              
            </span>
          </div>
          <div role="listbox" class="list-style-none" data-target="command-palette-item-group.list" aria-label="Access Policies results"></div>
        </command-palette-item-group>
            <command-palette-item-group data-group-id="organizations" data-group-title="Organizations" data-group-hint="" data-group-limits="{}" data-default-priority="8" data-catalyst="" class="py-2 border-top" hidden="true" data-skip-template="">
            
          <div class="d-flex flex-justify-between my-2 px-3">
            <span data-target="command-palette-item-group.header" class="color-fg-muted text-bold f6 text-normal">
              Organizations
            </span>
            <span data-target="command-palette-item-group.header" class="color-fg-muted f6 text-normal">
              
            </span>
          </div>
          <div role="listbox" class="list-style-none" data-target="command-palette-item-group.list" aria-label="Organizations results"></div>
        </command-palette-item-group>
            <command-palette-item-group data-group-id="repositories" data-group-title="Repositories" data-group-hint="" data-group-limits="{}" data-default-priority="9" data-catalyst="" class="py-2 border-top" hidden="true" data-skip-template="">
            
          <div class="d-flex flex-justify-between my-2 px-3">
            <span data-target="command-palette-item-group.header" class="color-fg-muted text-bold f6 text-normal">
              Repositories
            </span>
            <span data-target="command-palette-item-group.header" class="color-fg-muted f6 text-normal">
              
            </span>
          </div>
          <div role="listbox" class="list-style-none" data-target="command-palette-item-group.list" aria-label="Repositories results"></div>
        </command-palette-item-group>
            <command-palette-item-group data-group-id="references" data-group-title="Issues, pull requests, and discussions" data-group-hint="Type # to filter" data-group-limits="{}" data-default-priority="10" data-catalyst="" class="py-2 border-top" hidden="true" data-skip-template="">
            
          <div class="d-flex flex-justify-between my-2 px-3">
            <span data-target="command-palette-item-group.header" class="color-fg-muted text-bold f6 text-normal">
              Issues, pull requests, and discussions
            </span>
            <span data-target="command-palette-item-group.header" class="color-fg-muted f6 text-normal">
              Type # to filter
            </span>
          </div>
          <div role="listbox" class="list-style-none" data-target="command-palette-item-group.list" aria-label="Issues, pull requests, and discussions results"></div>
        </command-palette-item-group>
            <command-palette-item-group data-group-id="teams" data-group-title="Teams" data-group-hint="" data-group-limits="{}" data-default-priority="11" data-catalyst="" class="py-2 border-top" hidden="true" data-skip-template="">
            
          <div class="d-flex flex-justify-between my-2 px-3">
            <span data-target="command-palette-item-group.header" class="color-fg-muted text-bold f6 text-normal">
              Teams
            </span>
            <span data-target="command-palette-item-group.header" class="color-fg-muted f6 text-normal">
              
            </span>
          </div>
          <div role="listbox" class="list-style-none" data-target="command-palette-item-group.list" aria-label="Teams results"></div>
        </command-palette-item-group>
            <command-palette-item-group data-group-id="users" data-group-title="Users" data-group-hint="" data-group-limits="{}" data-default-priority="12" data-catalyst="" class="py-2 border-top" hidden="true" data-skip-template="">
            
          <div class="d-flex flex-justify-between my-2 px-3">
            <span data-target="command-palette-item-group.header" class="color-fg-muted text-bold f6 text-normal">
              Users
            </span>
            <span data-target="command-palette-item-group.header" class="color-fg-muted f6 text-normal">
              
            </span>
          </div>
          <div role="listbox" class="list-style-none" data-target="command-palette-item-group.list" aria-label="Users results"></div>
        </command-palette-item-group>
            <command-palette-item-group data-group-id="memex_projects" data-group-title="Projects" data-group-hint="" data-group-limits="{}" data-default-priority="13" data-catalyst="" class="py-2 border-top" hidden="true" data-skip-template="">
            
          <div class="d-flex flex-justify-between my-2 px-3">
            <span data-target="command-palette-item-group.header" class="color-fg-muted text-bold f6 text-normal">
              Projects
            </span>
            <span data-target="command-palette-item-group.header" class="color-fg-muted f6 text-normal">
              
            </span>
          </div>
          <div role="listbox" class="list-style-none" data-target="command-palette-item-group.list" aria-label="Projects results"></div>
        </command-palette-item-group>
            <command-palette-item-group data-group-id="projects" data-group-title="Projects (classic)" data-group-hint="" data-group-limits="{}" data-default-priority="14" data-catalyst="" class="py-2 border-top" hidden="true" data-skip-template="">
            
          <div class="d-flex flex-justify-between my-2 px-3">
            <span data-target="command-palette-item-group.header" class="color-fg-muted text-bold f6 text-normal">
              Projects (classic)
            </span>
            <span data-target="command-palette-item-group.header" class="color-fg-muted f6 text-normal">
              
            </span>
          </div>
          <div role="listbox" class="list-style-none" data-target="command-palette-item-group.list" aria-label="Projects (classic) results"></div>
        </command-palette-item-group>
            <command-palette-item-group data-group-id="footer" data-group-title="Footer" data-group-hint="" data-group-limits="{}" data-default-priority="15" data-catalyst="" class="py-2 border-top" hidden="true" data-skip-template="">
            
          <div role="listbox" class="list-style-none" data-target="command-palette-item-group.list" aria-label="Footer results"></div>
        </command-palette-item-group>
            <command-palette-item-group data-group-id="modes_help" data-group-title="Modes" data-group-hint="" data-group-limits="{}" data-default-priority="16" data-catalyst="" class="py-2 border-top" hidden="true" data-skip-template="">
            
          <div class="d-flex flex-justify-between my-2 px-3">
            <span data-target="command-palette-item-group.header" class="color-fg-muted text-bold f6 text-normal">
              Modes
            </span>
            <span data-target="command-palette-item-group.header" class="color-fg-muted f6 text-normal">
              
            </span>
          </div>
          <div role="listbox" class="list-style-none" data-target="command-palette-item-group.list" aria-label="Modes results"></div>
        </command-palette-item-group>
            <command-palette-item-group data-group-id="filters_help" data-group-title="Use filters in issues, pull requests, discussions, and projects" data-group-hint="" data-group-limits="{}" data-default-priority="17" data-catalyst="" class="py-2 border-top" hidden="true" data-skip-template="">
            
          <div class="d-flex flex-justify-between my-2 px-3">
            <span data-target="command-palette-item-group.header" class="color-fg-muted text-bold f6 text-normal">
              Use filters in issues, pull requests, discussions, and projects
            </span>
            <span data-target="command-palette-item-group.header" class="color-fg-muted f6 text-normal">
              
            </span>
          </div>
          <div role="listbox" class="list-style-none" data-target="command-palette-item-group.list" aria-label="Use filters in issues, pull requests, discussions, and projects results"></div>
        </command-palette-item-group>

            <command-palette-page data-page-title="bbottema" data-scope-id="MDQ6VXNlcjIxMTU3MTg=" data-scope-type="owner" data-targets="command-palette-page-stack.defaultPages" hidden="" data-catalyst="" class="rounded-bottom-2 page-stack-transition-height" style="max-height:400px;">
            </command-palette-page>
            <command-palette-page data-page-title="simple-java-mail" data-scope-id="MDEwOlJlcG9zaXRvcnkzNDEwMDQ0MQ==" data-scope-type="repository" data-targets="command-palette-page-stack.defaultPages" hidden="" data-catalyst="" class="rounded-bottom-2 page-stack-transition-height" style="max-height:400px;">
            </command-palette-page>
        </div>

        <command-palette-page data-is-root="" hidden="" data-page-title="" data-catalyst="" class="rounded-bottom-2 page-stack-transition-height" data-targets="command-palette-page-stack.pages" style="max-height:400px;" data-scope-id="" data-scope-type="">
        </command-palette-page>
          <command-palette-page data-page-title="bbottema" data-scope-id="MDQ6VXNlcjIxMTU3MTg=" data-scope-type="owner" hidden="" data-catalyst="" class="rounded-bottom-2 page-stack-transition-height" data-targets="command-palette-page-stack.pages" style="max-height:400px;">
          </command-palette-page>
          <command-palette-page data-page-title="simple-java-mail" data-scope-id="MDEwOlJlcG9zaXRvcnkzNDEwMDQ0MQ==" data-scope-type="repository" hidden="" data-catalyst="" class="rounded-bottom-2 page-stack-transition-height" data-targets="command-palette-page-stack.pages" style="max-height:400px;">
          </command-palette-page>
      </command-palette-page-stack>

      <server-defined-provider data-type="search-links" data-targets="command-palette.serverDefinedProviderElements" data-supported-modes="" data-catalyst="" data-fetch-debounce="" data-supported-scope-types="" data-src="" data-supports-commands=""></server-defined-provider>
      <server-defined-provider data-type="help" data-targets="command-palette.serverDefinedProviderElements" data-supported-modes="" data-catalyst="" data-fetch-debounce="" data-supported-scope-types="" data-src="" data-supports-commands="">
          <command-palette-help data-group="modes_help" data-prefix="#" data-scope-types="[&quot;&quot;]" data-catalyst="" hidden="">
            <span data-target="command-palette-help.titleElement">Search for <strong>issues</strong> and <strong>pull requests</strong></span>
              <span data-target="command-palette-help.hintElement">
                <kbd class="hx_kbd">#</kbd>
              </span>
          </command-palette-help>
          <command-palette-help data-group="modes_help" data-prefix="#" data-scope-types="[&quot;owner&quot;,&quot;repository&quot;]" data-catalyst="" hidden="">
            <span data-target="command-palette-help.titleElement">Search for <strong>issues, pull requests, discussions,</strong> and <strong>projects</strong></span>
              <span data-target="command-palette-help.hintElement">
                <kbd class="hx_kbd">#</kbd>
              </span>
          </command-palette-help>
          <command-palette-help data-group="modes_help" data-prefix="@" data-scope-types="[&quot;&quot;]" data-catalyst="" hidden="">
            <span data-target="command-palette-help.titleElement">Search for <strong>organizations, repositories,</strong> and <strong>users</strong></span>
              <span data-target="command-palette-help.hintElement">
                <kbd class="hx_kbd">@</kbd>
              </span>
          </command-palette-help>
          <command-palette-help data-group="modes_help" data-prefix="!" data-scope-types="[&quot;owner&quot;,&quot;repository&quot;]" data-catalyst="" hidden="">
            <span data-target="command-palette-help.titleElement">Search for <strong>projects</strong></span>
              <span data-target="command-palette-help.hintElement">
                <kbd class="hx_kbd">!</kbd>
              </span>
          </command-palette-help>
          <command-palette-help data-group="modes_help" data-prefix="/" data-scope-types="[&quot;repository&quot;]" data-catalyst="" hidden="">
            <span data-target="command-palette-help.titleElement">Search for <strong>files</strong></span>
              <span data-target="command-palette-help.hintElement">
                <kbd class="hx_kbd">/</kbd>
              </span>
          </command-palette-help>
          <command-palette-help data-group="modes_help" data-prefix=">" data-scope-types="" data-catalyst="" hidden="">
            <span data-target="command-palette-help.titleElement">Activate <strong>command mode</strong></span>
              <span data-target="command-palette-help.hintElement">
                <kbd class="hx_kbd">&gt;</kbd>
              </span>
          </command-palette-help>
          <command-palette-help data-group="filters_help" data-prefix="# author:@me" data-scope-types="" data-catalyst="" hidden="">
            <span data-target="command-palette-help.titleElement">Search your issues, pull requests, and discussions</span>
              <span data-target="command-palette-help.hintElement">
                <kbd class="hx_kbd"># author:@me</kbd>
              </span>
          </command-palette-help>
          <command-palette-help data-group="filters_help" data-prefix="# author:@me" data-scope-types="" data-catalyst="" hidden="">
            <span data-target="command-palette-help.titleElement">Search your issues, pull requests, and discussions</span>
              <span data-target="command-palette-help.hintElement">
                <kbd class="hx_kbd"># author:@me</kbd>
              </span>
          </command-palette-help>
          <command-palette-help data-group="filters_help" data-prefix="# is:pr" data-scope-types="" data-catalyst="" hidden="">
            <span data-target="command-palette-help.titleElement">Filter to pull requests</span>
              <span data-target="command-palette-help.hintElement">
                <kbd class="hx_kbd"># is:pr</kbd>
              </span>
          </command-palette-help>
          <command-palette-help data-group="filters_help" data-prefix="# is:issue" data-scope-types="" data-catalyst="" hidden="">
            <span data-target="command-palette-help.titleElement">Filter to issues</span>
              <span data-target="command-palette-help.hintElement">
                <kbd class="hx_kbd"># is:issue</kbd>
              </span>
          </command-palette-help>
          <command-palette-help data-group="filters_help" data-prefix="# is:discussion" data-scope-types="[&quot;owner&quot;,&quot;repository&quot;]" data-catalyst="" hidden="">
            <span data-target="command-palette-help.titleElement">Filter to discussions</span>
              <span data-target="command-palette-help.hintElement">
                <kbd class="hx_kbd"># is:discussion</kbd>
              </span>
          </command-palette-help>
          <command-palette-help data-group="filters_help" data-prefix="# is:project" data-scope-types="[&quot;owner&quot;,&quot;repository&quot;]" data-catalyst="" hidden="">
            <span data-target="command-palette-help.titleElement">Filter to projects</span>
              <span data-target="command-palette-help.hintElement">
                <kbd class="hx_kbd"># is:project</kbd>
              </span>
          </command-palette-help>
          <command-palette-help data-group="filters_help" data-prefix="# is:open" data-scope-types="" data-catalyst="" hidden="">
            <span data-target="command-palette-help.titleElement">Filter to open issues, pull requests, and discussions</span>
              <span data-target="command-palette-help.hintElement">
                <kbd class="hx_kbd"># is:open</kbd>
              </span>
          </command-palette-help>
      </server-defined-provider>

        <server-defined-provider data-type="commands" data-fetch-debounce="0" data-src="/command_palette/commands" data-supported-modes="[]" data-supports-commands="" data-targets="command-palette.serverDefinedProviderElements" data-supported-scope-types="" data-catalyst=""></server-defined-provider>
        <server-defined-provider data-type="prefetched" data-fetch-debounce="0" data-src="/command_palette/jump_to_page_navigation" data-supported-modes="[&quot;&quot;]" data-supported-scope-types="[&quot;&quot;,&quot;owner&quot;,&quot;repository&quot;]" data-targets="command-palette.serverDefinedProviderElements" data-supports-commands="" data-catalyst=""></server-defined-provider>
        <server-defined-provider data-type="remote" data-fetch-debounce="200" data-src="/command_palette/issues" data-supported-modes="[&quot;#&quot;,&quot;#&quot;]" data-supported-scope-types="[&quot;owner&quot;,&quot;repository&quot;,&quot;&quot;]" data-targets="command-palette.serverDefinedProviderElements" data-supports-commands="" data-catalyst=""></server-defined-provider>
        <server-defined-provider data-type="remote" data-fetch-debounce="200" data-src="/command_palette/jump_to" data-supported-modes="[&quot;@&quot;,&quot;@&quot;]" data-supported-scope-types="[&quot;&quot;,&quot;owner&quot;]" data-targets="command-palette.serverDefinedProviderElements" data-supports-commands="" data-catalyst=""></server-defined-provider>
        <server-defined-provider data-type="remote" data-fetch-debounce="200" data-src="/command_palette/jump_to_members_only" data-supported-modes="[&quot;@&quot;,&quot;@&quot;,&quot;&quot;,&quot;&quot;]" data-supported-scope-types="[&quot;&quot;,&quot;owner&quot;]" data-targets="command-palette.serverDefinedProviderElements" data-supports-commands="" data-catalyst=""></server-defined-provider>
        <server-defined-provider data-type="prefetched" data-fetch-debounce="0" data-src="/command_palette/jump_to_members_only_prefetched" data-supported-modes="[&quot;@&quot;,&quot;@&quot;,&quot;&quot;,&quot;&quot;]" data-supported-scope-types="[&quot;&quot;,&quot;owner&quot;]" data-targets="command-palette.serverDefinedProviderElements" data-supports-commands="" data-catalyst=""></server-defined-provider>
        <server-defined-provider data-type="files" data-fetch-debounce="0" data-src="/command_palette/files" data-supported-modes="[&quot;/&quot;]" data-supported-scope-types="[&quot;repository&quot;]" data-targets="command-palette.serverDefinedProviderElements" data-supports-commands="" data-catalyst=""></server-defined-provider>
        <server-defined-provider data-type="remote" data-fetch-debounce="200" data-src="/command_palette/discussions" data-supported-modes="[&quot;#&quot;]" data-supported-scope-types="[&quot;owner&quot;,&quot;repository&quot;]" data-targets="command-palette.serverDefinedProviderElements" data-supports-commands="" data-catalyst=""></server-defined-provider>
        <server-defined-provider data-type="remote" data-fetch-debounce="200" data-src="/command_palette/projects" data-supported-modes="[&quot;#&quot;,&quot;!&quot;]" data-supported-scope-types="[&quot;owner&quot;,&quot;repository&quot;]" data-targets="command-palette.serverDefinedProviderElements" data-supports-commands="" data-catalyst=""></server-defined-provider>
        <server-defined-provider data-type="prefetched" data-fetch-debounce="0" data-src="/command_palette/recent_issues" data-supported-modes="[&quot;#&quot;,&quot;#&quot;]" data-supported-scope-types="[&quot;owner&quot;,&quot;repository&quot;,&quot;&quot;]" data-targets="command-palette.serverDefinedProviderElements" data-supports-commands="" data-catalyst=""></server-defined-provider>
        <server-defined-provider data-type="remote" data-fetch-debounce="200" data-src="/command_palette/teams" data-supported-modes="[&quot;@&quot;,&quot;&quot;]" data-supported-scope-types="[&quot;owner&quot;]" data-targets="command-palette.serverDefinedProviderElements" data-supports-commands="" data-catalyst=""></server-defined-provider>
        <server-defined-provider data-type="remote" data-fetch-debounce="200" data-src="/command_palette/name_with_owner_repository" data-supported-modes="[&quot;@&quot;,&quot;@&quot;,&quot;&quot;,&quot;&quot;]" data-supported-scope-types="[&quot;&quot;,&quot;owner&quot;]" data-targets="command-palette.serverDefinedProviderElements" data-supports-commands="" data-catalyst=""></server-defined-provider>
    <client-defined-provider data-catalyst="" data-provider-id="main-window-commands-provider" data-targets="command-palette.clientDefinedProviderElements"></client-defined-provider></command-palette>
  </details-dialog>
</details>

<div class="position-fixed bottom-0 left-0 ml-5 mb-5 js-command-palette-toasts" style="z-index: 1000">
  <div hidden="" class="Toast Toast--loading">
    <span class="Toast-icon">
      <svg class="Toast--spinner" viewBox="0 0 32 32" width="18" height="18" aria-hidden="true">
        <path fill="#959da5" d="M16 0 A16 16 0 0 0 16 32 A16 16 0 0 0 16 0 M16 4 A12 12 0 0 1 16 28 A12 12 0 0 1 16 4"></path>
        <path fill="#ffffff" d="M16 0 A16 16 0 0 1 32 16 L28 16 A12 12 0 0 0 16 4z"></path>
      </svg>
    </span>
    <span class="Toast-content"></span>
  </div>

  <div hidden="" class="anim-fade-in fast Toast Toast--error">
    <span class="Toast-icon">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-stop">
    <path d="M4.47.22A.749.749 0 0 1 5 0h6c.199 0 .389.079.53.22l4.25 4.25c.141.14.22.331.22.53v6a.749.749 0 0 1-.22.53l-4.25 4.25A.749.749 0 0 1 11 16H5a.749.749 0 0 1-.53-.22L.22 11.53A.749.749 0 0 1 0 11V5c0-.199.079-.389.22-.53Zm.84 1.28L1.5 5.31v5.38l3.81 3.81h5.38l3.81-3.81V5.31L10.69 1.5ZM8 4a.75.75 0 0 1 .75.75v3.5a.75.75 0 0 1-1.5 0v-3.5A.75.75 0 0 1 8 4Zm0 8a1 1 0 1 1 0-2 1 1 0 0 1 0 2Z"></path>
</svg>
    </span>
    <span class="Toast-content"></span>
  </div>

  <div hidden="" class="anim-fade-in fast Toast Toast--warning">
    <span class="Toast-icon">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-alert">
    <path d="M6.457 1.047c.659-1.234 2.427-1.234 3.086 0l6.082 11.378A1.75 1.75 0 0 1 14.082 15H1.918a1.75 1.75 0 0 1-1.543-2.575Zm1.763.707a.25.25 0 0 0-.44 0L1.698 13.132a.25.25 0 0 0 .22.368h12.164a.25.25 0 0 0 .22-.368Zm.53 3.996v2.5a.75.75 0 0 1-1.5 0v-2.5a.75.75 0 0 1 1.5 0ZM9 11a1 1 0 1 1-2 0 1 1 0 0 1 2 0Z"></path>
</svg>
    </span>
    <span class="Toast-content"></span>
  </div>


  <div hidden="" class="anim-fade-in fast Toast Toast--success">
    <span class="Toast-icon">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </span>
    <span class="Toast-content"></span>
  </div>

  <div hidden="" class="anim-fade-in fast Toast">
    <span class="Toast-icon">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-info">
    <path d="M0 8a8 8 0 1 1 16 0A8 8 0 0 1 0 8Zm8-6.5a6.5 6.5 0 1 0 0 13 6.5 6.5 0 0 0 0-13ZM6.5 7.75A.75.75 0 0 1 7.25 7h1a.75.75 0 0 1 .75.75v2.75h.25a.75.75 0 0 1 0 1.5h-2a.75.75 0 0 1 0-1.5h.25v-2h-.25a.75.75 0 0 1-.75-.75ZM8 6a1 1 0 1 1 0-2 1 1 0 0 1 0 2Z"></path>
</svg>
    </span>
    <span class="Toast-content"></span>
  </div>
</div>


  <div class="application-main " data-commit-hovercards-enabled="" data-discussion-hovercards-enabled="" data-issue-and-pr-hovercards-enabled="">
        <div itemscope="" itemtype="http://schema.org/SoftwareSourceCode" class="">
    <main id="js-repo-pjax-container">
      
  


    






  
  <div id="repository-container-header" class="pt-3 hide-full-screen" style="background-color: var(--color-page-header-bg);" data-turbo-replace="">

      <div class="d-flex flex-wrap flex-justify-end mb-3  px-3 px-md-4 px-lg-5" style="gap: 1rem;">

        <div class="flex-auto min-width-0 width-fit mr-3">
            
  <div class=" d-flex flex-wrap flex-items-center wb-break-word f3 text-normal">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-repo color-fg-muted mr-2">
    <path d="M2 2.5A2.5 2.5 0 0 1 4.5 0h8.75a.75.75 0 0 1 .75.75v12.5a.75.75 0 0 1-.75.75h-2.5a.75.75 0 0 1 0-1.5h1.75v-2h-8a1 1 0 0 0-.714 1.7.75.75 0 1 1-1.072 1.05A2.495 2.495 0 0 1 2 11.5Zm10.5-1h-8a1 1 0 0 0-1 1v6.708A2.486 2.486 0 0 1 4.5 9h8ZM5 12.25a.25.25 0 0 1 .25-.25h3.5a.25.25 0 0 1 .25.25v3.25a.25.25 0 0 1-.4.2l-1.45-1.087a.249.249 0 0 0-.3 0L5.4 15.7a.25.25 0 0 1-.4-.2Z"></path>
</svg>
    
    <span class="author flex-self-stretch" itemprop="author">
      <a class="url fn" rel="author" data-hovercard-type="user" data-hovercard-url="/users/bbottema/hovercard" data-octo-click="hovercard-link-click" data-octo-dimensions="link_type:self" href="/bbottema">
        bbottema
</a>    </span>
    <span class="mx-1 flex-self-stretch color-fg-muted">/</span>
    <strong itemprop="name" class="mr-2 flex-self-stretch">
      <a data-pjax="#repo-content-pjax-container" data-turbo-frame="repo-content-turbo-frame" href="/bbottema/simple-java-mail">simple-java-mail</a>
    </strong>

    <span></span><span class="Label Label--secondary v-align-middle mr-1">Public</span>
  </div>


        </div>

        <div id="repository-details-container" data-turbo-replace="">
            <ul class="pagehead-actions flex-shrink-0 d-none d-md-inline" style="padding: 2px 0;">
    
        <li>
          <details id="funding-links-modal-bbottema-simple-java-mail" data-view-component="true" class="details-reset details-overlay details-overlay-dark d-inline-block float-left">
    <summary icon="heart" id="sponsor-button" title="Sponsor bbottema/simple-java-mail" aria-label="Sponsor bbottema/simple-java-mail" data-view-component="true" class="btn-sm btn" role="button">    <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-heart icon-sponsor mr-1 color-fg-sponsors">
    <path d="m8 14.25.345.666a.75.75 0 0 1-.69 0l-.008-.004-.018-.01a7.152 7.152 0 0 1-.31-.17 22.055 22.055 0 0 1-3.434-2.414C2.045 10.731 0 8.35 0 5.5 0 2.836 2.086 1 4.25 1 5.797 1 7.153 1.802 8 3.02 8.847 1.802 10.203 1 11.75 1 13.914 1 16 2.836 16 5.5c0 2.85-2.045 5.231-3.885 6.818a22.066 22.066 0 0 1-3.744 2.584l-.018.01-.006.003h-.002ZM4.25 2.5c-1.336 0-2.75 1.164-2.75 3 0 2.15 1.58 4.144 3.365 5.682A20.58 20.58 0 0 0 8 13.393a20.58 20.58 0 0 0 3.135-2.211C12.92 9.644 14.5 7.65 14.5 5.5c0-1.836-1.414-3-2.75-3-1.373 0-2.609.986-3.029 2.456a.749.749 0 0 1-1.442 0C6.859 3.486 5.623 2.5 4.25 2.5Z"></path>
</svg>
      Sponsor
</summary>
  <details-dialog aria-label="Sponsor dialog" class="anim-fade-in fast Box Box--overlay d-flex flex-column" src="/bbottema/simple-java-mail/funding_links?fragment=1" preload="" role="dialog" aria-modal="true">
    <div class="Box-header">
      <button class="Box-btn-octicon btn-octicon float-right" type="button" aria-label="Close dialog" data-close-dialog="">
        <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-x">
    <path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path>
</svg>
      </button>
      <h3 class="Box-title">
        Sponsor bbottema/simple-java-mail
      </h3>
    </div>
    <div class="overflow-auto">
      <include-fragment>
        <svg aria-label="Loading..." style="box-sizing: content-box; color: var(--color-icon-primary);" width="64" height="64" viewBox="0 0 16 16" fill="none" data-view-component="true" class="my-3 mx-auto d-block anim-rotate">
  <circle cx="8" cy="8" r="7" stroke="currentColor" stroke-opacity="0.25" stroke-width="2" vector-effect="non-scaling-stroke"></circle>
  <path d="M15 8a7.002 7.002 0 00-7-7" stroke="currentColor" stroke-width="2" stroke-linecap="round" vector-effect="non-scaling-stroke"></path>
</svg>
      </include-fragment>
    </div>
  </details-dialog>
</details>
        </li>

      

  <li>
              <notifications-list-subscription-form data-action="notifications-dialog-label-toggled:notifications-list-subscription-form#handleDialogLabelToggle" class="f5 position-relative" data-catalyst="">
        <details class="details-reset details-overlay f5 position-relative" data-target="notifications-list-subscription-form.details" data-action="toggle:notifications-list-subscription-form#detailsToggled">

          <summary data-hydro-click="{&quot;event_type&quot;:&quot;repository.click&quot;,&quot;payload&quot;:{&quot;target&quot;:&quot;WATCH_BUTTON&quot;,&quot;repository_id&quot;:34100441,&quot;originating_url&quot;:&quot;https://github.com/notifications/34100441/watch_subscription?aria_id_prefix=repository-details&amp;button_block=false&amp;show_count=true&quot;,&quot;user_id&quot;:99464989}}" data-hydro-click-hmac="04bb39b59f8a0414d0856ef671aae7256fa88444d164e47ded8c231efaf72e98" data-ga-click="Repository, click Watch settings, action:notifications#watch_subscription" aria-label="bbottema/simple-java-mail repository watch options" id="repository-details-watch-button" data-view-component="true" class="btn-sm btn" aria-haspopup="menu" role="button">    <span data-menu-button="">
              <span hidden="" data-target="notifications-list-subscription-form.unwatchButtonCopy">
                <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-eye">
    <path d="M8 2c1.981 0 3.671.992 4.933 2.078 1.27 1.091 2.187 2.345 2.637 3.023a1.62 1.62 0 0 1 0 1.798c-.45.678-1.367 1.932-2.637 3.023C11.67 13.008 9.981 14 8 14c-1.981 0-3.671-.992-4.933-2.078C1.797 10.83.88 9.576.43 8.898a1.62 1.62 0 0 1 0-1.798c.45-.677 1.367-1.931 2.637-3.022C4.33 2.992 6.019 2 8 2ZM1.679 7.932a.12.12 0 0 0 0 .136c.411.622 1.241 1.75 2.366 2.717C5.176 11.758 6.527 12.5 8 12.5c1.473 0 2.825-.742 3.955-1.715 1.124-.967 1.954-2.096 2.366-2.717a.12.12 0 0 0 0-.136c-.412-.621-1.242-1.75-2.366-2.717C10.824 4.242 9.473 3.5 8 3.5c-1.473 0-2.825.742-3.955 1.715-1.124.967-1.954 2.096-2.366 2.717ZM8 10a2 2 0 1 1-.001-3.999A2 2 0 0 1 8 10Z"></path>
</svg>
                Unwatch
              </span>
              <span hidden="" data-target="notifications-list-subscription-form.stopIgnoringButtonCopy">
                <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-bell-slash">
    <path d="m4.182 4.31.016.011 10.104 7.316.013.01 1.375.996a.75.75 0 1 1-.88 1.214L13.626 13H2.518a1.516 1.516 0 0 1-1.263-2.36l1.703-2.554A.255.255 0 0 0 3 7.947V5.305L.31 3.357a.75.75 0 1 1 .88-1.214Zm7.373 7.19L4.5 6.391v1.556c0 .346-.102.683-.294.97l-1.703 2.556a.017.017 0 0 0-.003.01c0 .005.002.009.005.012l.006.004.007.001ZM8 1.5c-.997 0-1.895.416-2.534 1.086A.75.75 0 1 1 4.38 1.55 5 5 0 0 1 13 5v2.373a.75.75 0 0 1-1.5 0V5A3.5 3.5 0 0 0 8 1.5ZM8 16a2 2 0 0 1-1.985-1.75c-.017-.137.097-.25.235-.25h3.5c.138 0 .252.113.235.25A2 2 0 0 1 8 16Z"></path>
</svg>
                Stop ignoring
              </span>
              <span data-target="notifications-list-subscription-form.watchButtonCopy">
                <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-eye">
    <path d="M8 2c1.981 0 3.671.992 4.933 2.078 1.27 1.091 2.187 2.345 2.637 3.023a1.62 1.62 0 0 1 0 1.798c-.45.678-1.367 1.932-2.637 3.023C11.67 13.008 9.981 14 8 14c-1.981 0-3.671-.992-4.933-2.078C1.797 10.83.88 9.576.43 8.898a1.62 1.62 0 0 1 0-1.798c.45-.677 1.367-1.931 2.637-3.022C4.33 2.992 6.019 2 8 2ZM1.679 7.932a.12.12 0 0 0 0 .136c.411.622 1.241 1.75 2.366 2.717C5.176 11.758 6.527 12.5 8 12.5c1.473 0 2.825-.742 3.955-1.715 1.124-.967 1.954-2.096 2.366-2.717a.12.12 0 0 0 0-.136c-.412-.621-1.242-1.75-2.366-2.717C10.824 4.242 9.473 3.5 8 3.5c-1.473 0-2.825.742-3.955 1.715-1.124.967-1.954 2.096-2.366 2.717ZM8 10a2 2 0 1 1-.001-3.999A2 2 0 0 1 8 10Z"></path>
</svg>
                Watch
              </span>
            </span>
              <span id="repo-notifications-counter" data-target="notifications-list-subscription-form.socialCount" data-pjax-replace="true" data-turbo-replace="true" title="36" data-view-component="true" class="Counter">36</span>
            <span class="dropdown-caret"></span>
</summary>
          <details-menu class="SelectMenu  " role="menu" data-target="notifications-list-subscription-form.menu" data-focus-trap="active"><span class="sentinel" tabindex="0" aria-hidden="true"></span>
            <div class="SelectMenu-modal notifications-component-menu-modal">
              <header class="SelectMenu-header">
                <h3 class="SelectMenu-title">Notifications</h3>
                <button class="SelectMenu-closeButton" type="button" aria-label="Close menu" data-action="click:notifications-list-subscription-form#closeMenu">
                  <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-x">
    <path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path>
</svg>
                </button>
              </header>

              <div class="SelectMenu-list">
                <!-- '"` --><!-- </textarea></xmp> --><form data-target="notifications-list-subscription-form.form" data-action="submit:notifications-list-subscription-form#submitForm" data-turbo="false" action="/notifications/subscribe" accept-charset="UTF-8" method="post"><input type="hidden" name="authenticity_token" value="l1YzxY7xLWbnubE4zX2aNpPXBKsKOmk55fKo5HSKR4-ANjuknpPqNmabGWG1hdg2sqmWEb22q5Zw31esGkkUFA" autocomplete="off">

                  <input type="hidden" name="repository_id" value="34100441">

                  <button type="submit" name="do" value="included" class="SelectMenu-item flex-items-start" role="menuitemradio" aria-checked="true" data-targets="notifications-list-subscription-form.subscriptionButtons">
                    <span class="f5">
                      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check SelectMenu-icon SelectMenu-icon--check">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
                    </span>
                    <div>
                      <div class="f5 text-bold">
                        Participating and @mentions
                      </div>
                      <div class="text-small color-fg-muted text-normal pb-1">
                        Only receive notifications from this repository when participating or @mentioned.
                      </div>
                    </div>
                  </button>

                  <button type="submit" name="do" value="subscribed" class="SelectMenu-item flex-items-start" role="menuitemradio" aria-checked="false" data-targets="notifications-list-subscription-form.subscriptionButtons">
                    <span class="f5">
                      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check SelectMenu-icon SelectMenu-icon--check">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
                    </span>
                    <div>
                      <div class="f5 text-bold">
                        All Activity
                      </div>
                      <div class="text-small color-fg-muted text-normal pb-1">
                        Notified of all notifications on this repository.
                      </div>
                    </div>
                  </button>

                  <button type="submit" name="do" value="ignore" class="SelectMenu-item flex-items-start" role="menuitemradio" aria-checked="false" data-targets="notifications-list-subscription-form.subscriptionButtons">
                    <span class="f5">
                      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check SelectMenu-icon SelectMenu-icon--check">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
                    </span>
                    <div>
                      <div class="f5 text-bold">
                        Ignore
                      </div>
                      <div class="text-small color-fg-muted text-normal pb-1">
                        Never be notified.
                      </div>
                    </div>
                  </button>
</form>
                <button class="SelectMenu-item flex-items-start pr-3" type="button" role="menuitemradio" data-target="notifications-list-subscription-form.customButton" data-action="click:notifications-list-subscription-form#openCustomDialog" aria-haspopup="true" aria-checked="false">
                  <span class="f5">
                    <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check SelectMenu-icon SelectMenu-icon--check">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
                  </span>
                  <div>
                    <div class="d-flex flex-items-start flex-justify-between">
                      <div class="f5 text-bold">Custom</div>
                      <div class="f5 pr-1">
                        <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-arrow-right">
    <path d="M8.22 2.97a.75.75 0 0 1 1.06 0l4.25 4.25a.75.75 0 0 1 0 1.06l-4.25 4.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042l2.97-2.97H3.75a.75.75 0 0 1 0-1.5h7.44L8.22 4.03a.75.75 0 0 1 0-1.06Z"></path>
</svg>
                      </div>
                    </div>
                    <div class="text-small color-fg-muted text-normal pb-1">
                      Select events you want to be notified of in addition to participating and @mentions.
                    </div>
                  </div>
                </button>

                  <div class="px-3 py-2 d-flex color-bg-subtle flex-items-center">
                    <span class="f5">
                      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-device-mobile SelectMenu-icon SelectMenu-icon--device-mobile">
    <path d="M3.75 0h8.5C13.216 0 14 .784 14 1.75v12.5A1.75 1.75 0 0 1 12.25 16h-8.5A1.75 1.75 0 0 1 2 14.25V1.75C2 .784 2.784 0 3.75 0ZM3.5 1.75v12.5c0 .138.112.25.25.25h8.5a.25.25 0 0 0 .25-.25V1.75a.25.25 0 0 0-.25-.25h-8.5a.25.25 0 0 0-.25.25ZM8 13a1 1 0 1 1 0-2 1 1 0 0 1 0 2Z"></path>
</svg>
                    </span>
                    <span classname="text-small color-fg-muted text-normal pb-1">
                      Get push notifications on <a target="_blank" rel="noopener noreferrer" href="https://apps.apple.com/app/apple-store/id1477376905?ct=watch-dropdown&amp;mt=8&amp;pt=524675">iOS</a> or <a target="_blank" rel="noopener noreferrer" href="https://play.google.com/store/apps/details?id=com.github.android&amp;referrer=utm_campaign%3Dwatch-dropdown%26utm_medium%3Dweb%26utm_source%3Dgithub">Android</a>.
                    </span>
                  </div>
              </div>
            </div>
          <span class="sentinel" tabindex="0" aria-hidden="true"></span></details-menu>

          <details-dialog class="notifications-component-dialog " data-target="notifications-list-subscription-form.customDialog" aria-label="Custom dialog" hidden="" role="dialog" aria-modal="true">
            <div class="SelectMenu-modal notifications-component-dialog-modal overflow-visible">
              <!-- '"` --><!-- </textarea></xmp> --><form data-target="notifications-list-subscription-form.customform" data-action="submit:notifications-list-subscription-form#submitCustomForm" data-turbo="false" action="/notifications/subscribe" accept-charset="UTF-8" method="post"><input type="hidden" name="authenticity_token" value="NRYMdFNx-_3lP4TyBRKvTPWNDCWFnNyIv4TFjrYYqCsidgQVQxM8rWQdLKt96u1M1POenzIQHicqqTrG2Nv7sA" autocomplete="off">

                <input type="hidden" name="repository_id" value="34100441">

                <header class="d-sm-none SelectMenu-header pb-0 border-bottom-0 px-2 px-sm-3">
                  <h1 class="f3 SelectMenu-title d-inline-flex">
                    <button class="color-bg-default border-0 px-2 py-0 m-0 Link--secondary f5" aria-label="Return to menu" type="button" data-action="click:notifications-list-subscription-form#closeCustomDialog">
                      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-arrow-left">
    <path d="M7.78 12.53a.75.75 0 0 1-1.06 0L2.47 8.28a.75.75 0 0 1 0-1.06l4.25-4.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042L4.81 7h7.44a.75.75 0 0 1 0 1.5H4.81l2.97 2.97a.75.75 0 0 1 0 1.06Z"></path>
</svg>
                    </button>
                    Custom
                  </h1>
                </header>

                <header class="d-none d-sm-flex flex-items-start pt-1">
                  <button class="border-0 px-2 pt-1 m-0 Link--secondary f5" style="background-color: transparent;" aria-label="Return to menu" type="button" data-action="click:notifications-list-subscription-form#closeCustomDialog">
                    <svg style="position: relative; left: 2px; top: 1px" aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-arrow-left">
    <path d="M7.78 12.53a.75.75 0 0 1-1.06 0L2.47 8.28a.75.75 0 0 1 0-1.06l4.25-4.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042L4.81 7h7.44a.75.75 0 0 1 0 1.5H4.81l2.97 2.97a.75.75 0 0 1 0 1.06Z"></path>
</svg>
                  </button>

                  <h1 class="pt-1 pr-4 pb-0 pl-0 f5 text-bold">
                    Custom
                  </h1>
                </header>

                <fieldset>
                  <legend>
                    <div class="text-small color-fg-muted pt-0 pr-3 pb-3 pl-6 pl-sm-5 border-bottom mb-3">
                      Select events you want to be notified of in addition to participating and @mentions.
                    </div>
                  </legend>
                  <div data-target="notifications-list-subscription-form.labelInputs">
                  </div>
                    <div class="form-checkbox mr-3 ml-6 ml-sm-5 mb-2 mt-0">
                      <label class="f5 text-normal">
                        <input type="checkbox" name="thread_types[]" value="Issue" data-targets="notifications-list-subscription-form.threadTypeCheckboxes" data-action="change:notifications-list-subscription-form#threadTypeCheckboxesUpdated">
                        Issues
                      </label>


                    </div>
                    <div class="form-checkbox mr-3 ml-6 ml-sm-5 mb-2 mt-0">
                      <label class="f5 text-normal">
                        <input type="checkbox" name="thread_types[]" value="PullRequest" data-targets="notifications-list-subscription-form.threadTypeCheckboxes" data-action="change:notifications-list-subscription-form#threadTypeCheckboxesUpdated">
                        Pull requests
                      </label>


                    </div>
                    <div class="form-checkbox mr-3 ml-6 ml-sm-5 mb-2 mt-0">
                      <label class="f5 text-normal">
                        <input type="checkbox" name="thread_types[]" value="Release" data-targets="notifications-list-subscription-form.threadTypeCheckboxes" data-action="change:notifications-list-subscription-form#threadTypeCheckboxesUpdated">
                        Releases
                      </label>


                    </div>
                    <div class="form-checkbox mr-3 ml-6 ml-sm-5 mb-2 mt-0">
                      <label class="f5 text-normal">
                        <input type="checkbox" name="thread_types[]" value="Discussion" data-targets="notifications-list-subscription-form.threadTypeCheckboxes" data-action="change:notifications-list-subscription-form#threadTypeCheckboxesUpdated" aria-describedby="Discussion-disabled" aria-disabled="true">
                        Discussions
                      </label>

                        <div id="Discussion-repository-details-disabled" class="color-fg-muted">
                          Discussions are not enabled for this repository
                        </div>

                    </div>
                    <div class="form-checkbox mr-3 ml-6 ml-sm-5 mb-2 mt-0">
                      <label class="f5 text-normal">
                        <input type="checkbox" name="thread_types[]" value="SecurityAlert" data-targets="notifications-list-subscription-form.threadTypeCheckboxes" data-action="change:notifications-list-subscription-form#threadTypeCheckboxesUpdated">
                        Security alerts
                      </label>


                    </div>
                </fieldset>
                <div class="pt-2 pb-3 px-3 d-flex flex-justify-start flex-row-reverse">
                    <button name="do" value="custom" data-target="notifications-list-subscription-form.customSubmit" disabled="disabled" type="submit" data-view-component="true" class="btn-primary btn-sm btn ml-2">    Apply
</button>

                    <button data-action="click:notifications-list-subscription-form#resetForm" data-close-dialog="" type="button" data-view-component="true" class="btn-sm btn">    Cancel
</button>
                </div>
</form>            </div>
          </details-dialog>


          <div class="notifications-component-dialog-overlay"></div>
        </details>
      </notifications-list-subscription-form>



  </li>

  <li>
        <div data-view-component="true" class="d-flex">
        <div data-view-component="true" class="position-relative d-inline-block">
    <a icon="repo-forked" id="fork-button" href="/bbottema/simple-java-mail/fork" data-hydro-click="{&quot;event_type&quot;:&quot;repository.click&quot;,&quot;payload&quot;:{&quot;target&quot;:&quot;FORK_BUTTON&quot;,&quot;repository_id&quot;:34100441,&quot;originating_url&quot;:&quot;https://github.com/bbottema/simple-java-mail/blob/master/README.md&quot;,&quot;user_id&quot;:99464989}}" data-hydro-click-hmac="e203752afc414c023be6fc682e68ae09871ffaeaa35c5db001bac0a71d9b39a5" data-ga-click="Repository, show fork modal, action:blob#show; text:Fork" data-view-component="true" class="btn-sm btn BtnGroup-item border-right-0" aria-describedby="tooltip-9beff441-9bcc-4a6d-a021-cfa885815e21">      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-repo-forked mr-2">
    <path d="M5 5.372v.878c0 .414.336.75.75.75h4.5a.75.75 0 0 0 .75-.75v-.878a2.25 2.25 0 1 1 1.5 0v.878a2.25 2.25 0 0 1-2.25 2.25h-1.5v2.128a2.251 2.251 0 1 1-1.5 0V8.5h-1.5A2.25 2.25 0 0 1 3.5 6.25v-.878a2.25 2.25 0 1 1 1.5 0ZM5 3.25a.75.75 0 1 0-1.5 0 .75.75 0 0 0 1.5 0Zm6.75.75a.75.75 0 1 0 0-1.5.75.75 0 0 0 0 1.5Zm-3 8.75a.75.75 0 1 0-1.5 0 .75.75 0 0 0 1.5 0Z"></path>
</svg>Fork
          <span id="repo-network-counter" data-pjax-replace="true" data-turbo-replace="true" title="249" data-view-component="true" class="Counter">249</span>
</a>    <tool-tip id="tooltip-9beff441-9bcc-4a6d-a021-cfa885815e21" for="fork-button" data-direction="s" data-type="description" data-view-component="true" class="sr-only position-absolute" role="tooltip">Fork your own copy of bbottema/simple-java-mail</tool-tip>
</div>
      <details group_item="true" id="my-forks-menu-34100441" data-view-component="true" class="details-reset details-overlay BtnGroup-parent d-inline-block position-relative">
              <summary aria-label="See your forks of this repository" data-view-component="true" class="btn-sm btn BtnGroup-item px-2 float-none" aria-haspopup="menu" role="button">    <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-triangle-down">
    <path d="m4.427 7.427 3.396 3.396a.25.25 0 0 0 .354 0l3.396-3.396A.25.25 0 0 0 11.396 7H4.604a.25.25 0 0 0-.177.427Z"></path>
</svg>
</summary>
  <details-menu class="SelectMenu right-0" src="/bbottema/simple-java-mail/my_forks_menu_content?can_fork=true" role="menu" data-focus-trap="suspended"><span class="sentinel" tabindex="0" aria-hidden="true"></span>
    <div class="SelectMenu-modal">
        <button class="SelectMenu-closeButton position-absolute right-0 m-2" type="button" aria-label="Close menu" data-toggle-for="details-9debc3">
          <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-x">
    <path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path>
</svg>
        </button>
      <div id="filter-menu-9debc3" class="d-flex flex-column flex-1 overflow-hidden">
        <div class="SelectMenu-list">

            <include-fragment class="SelectMenu-loading" aria-label="Loading">
              <svg role="menuitem" style="box-sizing: content-box; color: var(--color-icon-primary);" width="32" height="32" viewBox="0 0 16 16" fill="none" data-view-component="true" class="anim-rotate">
  <circle cx="8" cy="8" r="7" stroke="currentColor" stroke-opacity="0.25" stroke-width="2" vector-effect="non-scaling-stroke"></circle>
  <path d="M15 8a7.002 7.002 0 00-7-7" stroke="currentColor" stroke-width="2" stroke-linecap="round" vector-effect="non-scaling-stroke"></path>
</svg>
            </include-fragment>
        </div>
        
      </div>
    </div>
  <span class="sentinel" tabindex="0" aria-hidden="true"></span></details-menu>
</details></div>
  </li>

  <li>
        <template class="js-unstar-confirmation-dialog-template">
  <div class="Box-header">
    <h2 class="Box-title">Unstar this repository?</h2>
  </div>
  <div class="Box-body">
    <p class="mb-3">
      This will remove {{ repoNameWithOwner }} from the {{ listsWithCount }} that it's been added to.
    </p>
    <div class="form-actions">
      <!-- '"` --><!-- </textarea></xmp> --><form class="js-social-confirmation-form" data-turbo="false" action="{{ confirmUrl }}" accept-charset="UTF-8" method="post">
        <input type="hidden" name="authenticity_token" value="{{ confirmCsrfToken }}">
        <input type="hidden" name="confirm" value="true">
          <button data-close-dialog="true" type="submit" data-view-component="true" class="btn-danger btn width-full">    Unstar
</button>
</form>    </div>
  </div>
</template>

  <div data-view-component="true" class="js-toggler-container js-social-container starring-container d-flex">
    <div data-view-component="true" class="starred BtnGroup flex-1">
      <!-- '"` --><!-- </textarea></xmp> --><form class="js-social-form BtnGroup-parent flex-auto js-deferred-toggler-target" data-turbo="false" action="/bbottema/simple-java-mail/unstar" accept-charset="UTF-8" method="post"><input type="hidden" name="authenticity_token" value="bfcWNCvEQWDgo7O3gFg9A1hrU6Fttxh9r8M5x-8eE7HnbRGIpV5dnkWGaiqvcUav0r2zkcfqb0QF1PKN4jlUOg" autocomplete="off">
          <input type="hidden" value="KP97rKmZQSugBj7tJkqmJh19sW1cAnvtJIJh9i2bfaqiZXwQJwNd1QUj53AJY92Kl6tRXfZfDNSOlaq8ILw6IQ" data-csrf="true" class="js-confirm-csrf-token">
        <input type="hidden" name="context" value="repository">
          <button data-hydro-click="{&quot;event_type&quot;:&quot;repository.click&quot;,&quot;payload&quot;:{&quot;target&quot;:&quot;UNSTAR_BUTTON&quot;,&quot;repository_id&quot;:34100441,&quot;originating_url&quot;:&quot;https://github.com/bbottema/simple-java-mail/blob/master/README.md&quot;,&quot;user_id&quot;:99464989}}" data-hydro-click-hmac="0299d68adc022ec771445cbc2e1836537b076e6d80da2c782ba7d647f10cdd9b" data-ga-click="Repository, click unstar button, action:blob#show; text:Unstar" aria-label="Unstar this repository (1079)" type="submit" data-view-component="true" class="rounded-left-2 btn-sm btn BtnGroup-item">    <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-star-fill starred-button-icon d-inline-block mr-2">
    <path d="M8 .25a.75.75 0 0 1 .673.418l1.882 3.815 4.21.612a.75.75 0 0 1 .416 1.279l-3.046 2.97.719 4.192a.751.751 0 0 1-1.088.791L8 12.347l-3.766 1.98a.75.75 0 0 1-1.088-.79l.72-4.194L.818 6.374a.75.75 0 0 1 .416-1.28l4.21-.611L7.327.668A.75.75 0 0 1 8 .25Z"></path>
</svg><span data-view-component="true" class="d-inline">
              Starred
</span>              <span id="repo-stars-counter-unstar" aria-label="1079 users starred this repository" data-singular-suffix="user starred this repository" data-plural-suffix="users starred this repository" data-turbo-replace="true" title="1,079" data-view-component="true" class="Counter js-social-count">1.1k</span>
</button></form>        <details id="details-user-list-34100441-starred" data-view-component="true" class="details-reset details-overlay BtnGroup-parent js-user-list-menu d-inline-block position-relative">
        <summary aria-label="Add this repository to a list" data-view-component="true" class="btn-sm btn BtnGroup-item px-2 float-none" aria-haspopup="menu" role="button">    <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-triangle-down">
    <path d="m4.427 7.427 3.396 3.396a.25.25 0 0 0 .354 0l3.396-3.396A.25.25 0 0 0 11.396 7H4.604a.25.25 0 0 0-.177.427Z"></path>
</svg>
</summary>
  <details-menu class="SelectMenu right-0" src="/bbottema/simple-java-mail/lists" role="menu" data-focus-trap="suspended"><span class="sentinel" tabindex="0" aria-hidden="true"></span>
    <div class="SelectMenu-modal">
        <button class="SelectMenu-closeButton position-absolute right-0 m-2" type="button" aria-label="Close menu" data-toggle-for="details-b373b7">
          <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-x">
    <path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path>
</svg>
        </button>
      <div id="filter-menu-b373b7" class="d-flex flex-column flex-1 overflow-hidden">
        <div class="SelectMenu-list">

            <include-fragment class="SelectMenu-loading" aria-label="Loading">
              <svg role="menuitem" style="box-sizing: content-box; color: var(--color-icon-primary);" width="32" height="32" viewBox="0 0 16 16" fill="none" data-view-component="true" class="anim-rotate">
  <circle cx="8" cy="8" r="7" stroke="currentColor" stroke-opacity="0.25" stroke-width="2" vector-effect="non-scaling-stroke"></circle>
  <path d="M15 8a7.002 7.002 0 00-7-7" stroke="currentColor" stroke-width="2" stroke-linecap="round" vector-effect="non-scaling-stroke"></path>
</svg>
            </include-fragment>
        </div>
        
      </div>
    </div>
  <span class="sentinel" tabindex="0" aria-hidden="true"></span></details-menu>
</details>
</div>
    <div data-view-component="true" class="unstarred BtnGroup flex-1">
      <!-- '"` --><!-- </textarea></xmp> --><form class="js-social-form BtnGroup-parent flex-auto" data-turbo="false" action="/bbottema/simple-java-mail/star" accept-charset="UTF-8" method="post"><input type="hidden" name="authenticity_token" value="94gSYTt5KqCjAZ5hW6S3n1qQD5TiLtoT5XzNnnIgeBCvtAHX4wK7igPOH8Mc_O0kLIwnIJ4QRtk5Ub1dTBe9wQ" autocomplete="off">
        <input type="hidden" name="context" value="repository">
          <button data-hydro-click="{&quot;event_type&quot;:&quot;repository.click&quot;,&quot;payload&quot;:{&quot;target&quot;:&quot;STAR_BUTTON&quot;,&quot;repository_id&quot;:34100441,&quot;originating_url&quot;:&quot;https://github.com/bbottema/simple-java-mail/blob/master/README.md&quot;,&quot;user_id&quot;:99464989}}" data-hydro-click-hmac="3f1e2bcf26ca68658d6a9193474aca5e3055091193dcb93643f351db48af936c" data-ga-click="Repository, click star button, action:blob#show; text:Star" aria-label="Star this repository (1079)" type="submit" data-view-component="true" class="js-toggler-target rounded-left-2 btn-sm btn BtnGroup-item">    <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-star d-inline-block mr-2">
    <path d="M8 .25a.75.75 0 0 1 .673.418l1.882 3.815 4.21.612a.75.75 0 0 1 .416 1.279l-3.046 2.97.719 4.192a.751.751 0 0 1-1.088.791L8 12.347l-3.766 1.98a.75.75 0 0 1-1.088-.79l.72-4.194L.818 6.374a.75.75 0 0 1 .416-1.28l4.21-.611L7.327.668A.75.75 0 0 1 8 .25Zm0 2.445L6.615 5.5a.75.75 0 0 1-.564.41l-3.097.45 2.24 2.184a.75.75 0 0 1 .216.664l-.528 3.084 2.769-1.456a.75.75 0 0 1 .698 0l2.77 1.456-.53-3.084a.75.75 0 0 1 .216-.664l2.24-2.183-3.096-.45a.75.75 0 0 1-.564-.41L8 2.694Z"></path>
</svg><span data-view-component="true" class="d-inline">
              Star
</span>              <span id="repo-stars-counter-star" aria-label="1079 users starred this repository" data-singular-suffix="user starred this repository" data-plural-suffix="users starred this repository" data-turbo-replace="true" title="1,079" data-view-component="true" class="Counter js-social-count">1.1k</span>
</button></form>        <details id="details-user-list-34100441-unstarred" data-view-component="true" class="details-reset details-overlay BtnGroup-parent js-user-list-menu d-inline-block position-relative">
        <summary aria-label="Add this repository to a list" data-view-component="true" class="btn-sm btn BtnGroup-item px-2 float-none" aria-haspopup="menu" role="button">    <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-triangle-down">
    <path d="m4.427 7.427 3.396 3.396a.25.25 0 0 0 .354 0l3.396-3.396A.25.25 0 0 0 11.396 7H4.604a.25.25 0 0 0-.177.427Z"></path>
</svg>
</summary>
  <details-menu class="SelectMenu right-0" src="/bbottema/simple-java-mail/lists" role="menu" data-focus-trap="suspended"><span class="sentinel" tabindex="0" aria-hidden="true"></span>
    <div class="SelectMenu-modal">
        <button class="SelectMenu-closeButton position-absolute right-0 m-2" type="button" aria-label="Close menu" data-toggle-for="details-c47dce">
          <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-x">
    <path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path>
</svg>
        </button>
      <div id="filter-menu-c47dce" class="d-flex flex-column flex-1 overflow-hidden">
        <div class="SelectMenu-list">

            <include-fragment class="SelectMenu-loading" aria-label="Loading">
              <svg role="menuitem" style="box-sizing: content-box; color: var(--color-icon-primary);" width="32" height="32" viewBox="0 0 16 16" fill="none" data-view-component="true" class="anim-rotate">
  <circle cx="8" cy="8" r="7" stroke="currentColor" stroke-opacity="0.25" stroke-width="2" vector-effect="non-scaling-stroke"></circle>
  <path d="M15 8a7.002 7.002 0 00-7-7" stroke="currentColor" stroke-width="2" stroke-linecap="round" vector-effect="non-scaling-stroke"></path>
</svg>
            </include-fragment>
        </div>
        
      </div>
    </div>
  <span class="sentinel" tabindex="0" aria-hidden="true"></span></details-menu>
</details>
</div></div>
  </li>


    

</ul>

        </div>
      </div>

        <div id="responsive-meta-container" data-turbo-replace="">
</div>


          <nav data-pjax="#js-repo-pjax-container" aria-label="Repository" data-view-component="true" class="js-repo-nav js-sidenav-container-pjax js-responsive-underlinenav overflow-hidden UnderlineNav px-3 px-md-4 px-lg-5">

  <ul data-view-component="true" class="UnderlineNav-body list-style-none">
      <li data-view-component="true" class="d-inline-flex">
  <a id="code-tab" href="/bbottema/simple-java-mail" data-tab-item="i0code-tab" data-selected-links="repo_source repo_downloads repo_commits repo_releases repo_tags repo_branches repo_packages repo_deployments /bbottema/simple-java-mail" data-pjax="#repo-content-pjax-container" data-turbo-frame="repo-content-turbo-frame" data-hotkey="g c" data-analytics-event="{&quot;category&quot;:&quot;Underline navbar&quot;,&quot;action&quot;:&quot;Click tab&quot;,&quot;label&quot;:&quot;Code&quot;,&quot;target&quot;:&quot;UNDERLINE_NAV.TAB&quot;}" aria-current="page" data-view-component="true" class="UnderlineNav-item no-wrap js-responsive-underlinenav-item js-selected-navigation-item selected">
    
              <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-code UnderlineNav-octicon d-none d-sm-inline">
    <path d="m11.28 3.22 4.25 4.25a.75.75 0 0 1 0 1.06l-4.25 4.25a.749.749 0 0 1-1.275-.326.749.749 0 0 1 .215-.734L13.94 8l-3.72-3.72a.749.749 0 0 1 .326-1.275.749.749 0 0 1 .734.215Zm-6.56 0a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042L2.06 8l3.72 3.72a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L.47 8.53a.75.75 0 0 1 0-1.06Z"></path>
</svg>
        <span data-content="Code">Code</span>
          <span id="code-repo-tab-count" data-pjax-replace="" data-turbo-replace="" title="Not available" data-view-component="true" class="Counter"></span>


    
</a></li>
      <li data-view-component="true" class="d-inline-flex">
  <a id="issues-tab" href="/bbottema/simple-java-mail/issues" data-tab-item="i1issues-tab" data-selected-links="repo_issues repo_labels repo_milestones /bbottema/simple-java-mail/issues" data-pjax="#repo-content-pjax-container" data-turbo-frame="repo-content-turbo-frame" data-hotkey="g i" data-analytics-event="{&quot;category&quot;:&quot;Underline navbar&quot;,&quot;action&quot;:&quot;Click tab&quot;,&quot;label&quot;:&quot;Issues&quot;,&quot;target&quot;:&quot;UNDERLINE_NAV.TAB&quot;}" data-view-component="true" class="UnderlineNav-item no-wrap js-responsive-underlinenav-item js-selected-navigation-item">
    
              <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-issue-opened UnderlineNav-octicon d-none d-sm-inline">
    <path d="M8 9.5a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3Z"></path><path d="M8 0a8 8 0 1 1 0 16A8 8 0 0 1 8 0ZM1.5 8a6.5 6.5 0 1 0 13 0 6.5 6.5 0 0 0-13 0Z"></path>
</svg>
        <span data-content="Issues">Issues</span>
          <span id="issues-repo-tab-count" data-pjax-replace="" data-turbo-replace="" title="14" data-view-component="true" class="Counter">14</span>


    
</a></li>
      <li data-view-component="true" class="d-inline-flex">
  <a id="pull-requests-tab" href="/bbottema/simple-java-mail/pulls" data-tab-item="i2pull-requests-tab" data-selected-links="repo_pulls checks /bbottema/simple-java-mail/pulls" data-pjax="#repo-content-pjax-container" data-turbo-frame="repo-content-turbo-frame" data-hotkey="g p" data-analytics-event="{&quot;category&quot;:&quot;Underline navbar&quot;,&quot;action&quot;:&quot;Click tab&quot;,&quot;label&quot;:&quot;Pull requests&quot;,&quot;target&quot;:&quot;UNDERLINE_NAV.TAB&quot;}" data-view-component="true" class="UnderlineNav-item no-wrap js-responsive-underlinenav-item js-selected-navigation-item">
    
              <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-git-pull-request UnderlineNav-octicon d-none d-sm-inline">
    <path d="M1.5 3.25a2.25 2.25 0 1 1 3 2.122v5.256a2.251 2.251 0 1 1-1.5 0V5.372A2.25 2.25 0 0 1 1.5 3.25Zm5.677-.177L9.573.677A.25.25 0 0 1 10 .854V2.5h1A2.5 2.5 0 0 1 13.5 5v5.628a2.251 2.251 0 1 1-1.5 0V5a1 1 0 0 0-1-1h-1v1.646a.25.25 0 0 1-.427.177L7.177 3.427a.25.25 0 0 1 0-.354ZM3.75 2.5a.75.75 0 1 0 0 1.5.75.75 0 0 0 0-1.5Zm0 9.5a.75.75 0 1 0 0 1.5.75.75 0 0 0 0-1.5Zm8.25.75a.75.75 0 1 0 1.5 0 .75.75 0 0 0-1.5 0Z"></path>
</svg>
        <span data-content="Pull requests">Pull requests</span>
          <span id="pull-requests-repo-tab-count" data-pjax-replace="" data-turbo-replace="" title="0" hidden="hidden" data-view-component="true" class="Counter">0</span>


    
</a></li>
      <li data-view-component="true" class="d-inline-flex">
  <a id="actions-tab" href="/bbottema/simple-java-mail/actions" data-tab-item="i3actions-tab" data-selected-links="repo_actions /bbottema/simple-java-mail/actions" data-pjax="#repo-content-pjax-container" data-turbo-frame="repo-content-turbo-frame" data-hotkey="g a" data-analytics-event="{&quot;category&quot;:&quot;Underline navbar&quot;,&quot;action&quot;:&quot;Click tab&quot;,&quot;label&quot;:&quot;Actions&quot;,&quot;target&quot;:&quot;UNDERLINE_NAV.TAB&quot;}" data-view-component="true" class="UnderlineNav-item no-wrap js-responsive-underlinenav-item js-selected-navigation-item" style="visibility: hidden;">
    
              <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-play UnderlineNav-octicon d-none d-sm-inline">
    <path d="M8 0a8 8 0 1 1 0 16A8 8 0 0 1 8 0ZM1.5 8a6.5 6.5 0 1 0 13 0 6.5 6.5 0 0 0-13 0Zm4.879-2.773 4.264 2.559a.25.25 0 0 1 0 .428l-4.264 2.559A.25.25 0 0 1 6 10.559V5.442a.25.25 0 0 1 .379-.215Z"></path>
</svg>
        <span data-content="Actions">Actions</span>
          <span id="actions-repo-tab-count" data-pjax-replace="" data-turbo-replace="" title="Not available" data-view-component="true" class="Counter"></span>


    
</a></li>
      <li data-view-component="true" class="d-inline-flex">
  <a id="projects-tab" href="/bbottema/simple-java-mail/projects" data-tab-item="i4projects-tab" data-selected-links="repo_projects new_repo_project repo_project /bbottema/simple-java-mail/projects" data-pjax="#repo-content-pjax-container" data-turbo-frame="repo-content-turbo-frame" data-hotkey="g b" data-analytics-event="{&quot;category&quot;:&quot;Underline navbar&quot;,&quot;action&quot;:&quot;Click tab&quot;,&quot;label&quot;:&quot;Projects&quot;,&quot;target&quot;:&quot;UNDERLINE_NAV.TAB&quot;}" data-view-component="true" class="UnderlineNav-item no-wrap js-responsive-underlinenav-item js-selected-navigation-item" style="visibility: hidden;">
    
              <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-table UnderlineNav-octicon d-none d-sm-inline">
    <path d="M0 1.75C0 .784.784 0 1.75 0h12.5C15.216 0 16 .784 16 1.75v12.5A1.75 1.75 0 0 1 14.25 16H1.75A1.75 1.75 0 0 1 0 14.25ZM6.5 6.5v8h7.75a.25.25 0 0 0 .25-.25V6.5Zm8-1.5V1.75a.25.25 0 0 0-.25-.25H6.5V5Zm-13 1.5v7.75c0 .138.112.25.25.25H5v-8ZM5 5V1.5H1.75a.25.25 0 0 0-.25.25V5Z"></path>
</svg>
        <span data-content="Projects">Projects</span>
          <span id="projects-repo-tab-count" data-pjax-replace="" data-turbo-replace="" title="0" hidden="hidden" data-view-component="true" class="Counter">0</span>


    
</a></li>
      <li data-view-component="true" class="d-inline-flex">
  <a id="security-tab" href="/bbottema/simple-java-mail/security" data-tab-item="i5security-tab" data-selected-links="security overview alerts policy token_scanning code_scanning /bbottema/simple-java-mail/security" data-pjax="#repo-content-pjax-container" data-turbo-frame="repo-content-turbo-frame" data-hotkey="g s" data-analytics-event="{&quot;category&quot;:&quot;Underline navbar&quot;,&quot;action&quot;:&quot;Click tab&quot;,&quot;label&quot;:&quot;Security&quot;,&quot;target&quot;:&quot;UNDERLINE_NAV.TAB&quot;}" data-view-component="true" class="UnderlineNav-item no-wrap js-responsive-underlinenav-item js-selected-navigation-item" style="visibility: hidden;">
    
              <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-shield UnderlineNav-octicon d-none d-sm-inline">
    <path d="M7.467.133a1.748 1.748 0 0 1 1.066 0l5.25 1.68A1.75 1.75 0 0 1 15 3.48V7c0 1.566-.32 3.182-1.303 4.682-.983 1.498-2.585 2.813-5.032 3.855a1.697 1.697 0 0 1-1.33 0c-2.447-1.042-4.049-2.357-5.032-3.855C1.32 10.182 1 8.566 1 7V3.48a1.75 1.75 0 0 1 1.217-1.667Zm.61 1.429a.25.25 0 0 0-.153 0l-5.25 1.68a.25.25 0 0 0-.174.238V7c0 1.358.275 2.666 1.057 3.86.784 1.194 2.121 2.34 4.366 3.297a.196.196 0 0 0 .154 0c2.245-.956 3.582-2.104 4.366-3.298C13.225 9.666 13.5 8.36 13.5 7V3.48a.251.251 0 0 0-.174-.237l-5.25-1.68ZM8.75 4.75v3a.75.75 0 0 1-1.5 0v-3a.75.75 0 0 1 1.5 0ZM9 10.5a1 1 0 1 1-2 0 1 1 0 0 1 2 0Z"></path>
</svg>
        <span data-content="Security">Security</span>
          

    
</a></li>
      <li data-view-component="true" class="d-inline-flex">
  <a id="insights-tab" href="/bbottema/simple-java-mail/pulse" data-tab-item="i6insights-tab" data-selected-links="repo_graphs repo_contributors dependency_graph dependabot_updates pulse people community /bbottema/simple-java-mail/pulse" data-pjax="#repo-content-pjax-container" data-turbo-frame="repo-content-turbo-frame" data-analytics-event="{&quot;category&quot;:&quot;Underline navbar&quot;,&quot;action&quot;:&quot;Click tab&quot;,&quot;label&quot;:&quot;Insights&quot;,&quot;target&quot;:&quot;UNDERLINE_NAV.TAB&quot;}" data-view-component="true" class="UnderlineNav-item no-wrap js-responsive-underlinenav-item js-selected-navigation-item" style="visibility: hidden;">
    
              <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-graph UnderlineNav-octicon d-none d-sm-inline">
    <path d="M1.5 1.75V13.5h13.75a.75.75 0 0 1 0 1.5H.75a.75.75 0 0 1-.75-.75V1.75a.75.75 0 0 1 1.5 0Zm14.28 2.53-5.25 5.25a.75.75 0 0 1-1.06 0L7 7.06 4.28 9.78a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042l3.25-3.25a.75.75 0 0 1 1.06 0L10 7.94l4.72-4.72a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042Z"></path>
</svg>
        <span data-content="Insights">Insights</span>
          <span id="insights-repo-tab-count" data-pjax-replace="" data-turbo-replace="" title="Not available" data-view-component="true" class="Counter"></span>


    
</a></li>
</ul>
    <div style="" data-view-component="true" class="UnderlineNav-actions js-responsive-underlinenav-overflow position-absolute pr-3 pr-md-4 pr-lg-5 right-0">      <details data-view-component="true" class="details-overlay details-reset position-relative">
  <summary role="button" data-view-component="true" aria-haspopup="menu">          <div class="UnderlineNav-item mr-0 border-0">
            <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-kebab-horizontal">
    <path d="M8 9a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3ZM1.5 9a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3Zm13 0a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3Z"></path>
</svg>
            <span class="sr-only">More</span>
          </div>
</summary>
  <details-menu role="menu" data-view-component="true" class="dropdown-menu dropdown-menu-sw" data-focus-trap="suspended"><span class="sentinel" tabindex="0" aria-hidden="true"></span>          <ul>
              <li data-menu-item="i0code-tab" hidden="">
                <a role="menuitem" class="js-selected-navigation-item selected dropdown-item" aria-current="page" data-selected-links="repo_source repo_downloads repo_commits repo_releases repo_tags repo_branches repo_packages repo_deployments /bbottema/simple-java-mail" href="/bbottema/simple-java-mail">
                  Code
</a>              </li>
              <li data-menu-item="i1issues-tab" hidden="">
                <a role="menuitem" class="js-selected-navigation-item dropdown-item" data-selected-links="repo_issues repo_labels repo_milestones /bbottema/simple-java-mail/issues" href="/bbottema/simple-java-mail/issues">
                  Issues
</a>              </li>
              <li data-menu-item="i2pull-requests-tab" hidden="">
                <a role="menuitem" class="js-selected-navigation-item dropdown-item" data-selected-links="repo_pulls checks /bbottema/simple-java-mail/pulls" href="/bbottema/simple-java-mail/pulls">
                  Pull requests
</a>              </li>
              <li data-menu-item="i3actions-tab">
                <a role="menuitem" class="js-selected-navigation-item dropdown-item" data-selected-links="repo_actions /bbottema/simple-java-mail/actions" href="/bbottema/simple-java-mail/actions">
                  Actions
</a>              </li>
              <li data-menu-item="i4projects-tab">
                <a role="menuitem" class="js-selected-navigation-item dropdown-item" data-selected-links="repo_projects new_repo_project repo_project /bbottema/simple-java-mail/projects" href="/bbottema/simple-java-mail/projects">
                  Projects
</a>              </li>
              <li data-menu-item="i5security-tab">
                <a role="menuitem" class="js-selected-navigation-item dropdown-item" data-selected-links="security overview alerts policy token_scanning code_scanning /bbottema/simple-java-mail/security" href="/bbottema/simple-java-mail/security">
                  Security
</a>              </li>
              <li data-menu-item="i6insights-tab">
                <a role="menuitem" class="js-selected-navigation-item dropdown-item" data-selected-links="repo_graphs repo_contributors dependency_graph dependabot_updates pulse people community /bbottema/simple-java-mail/pulse" href="/bbottema/simple-java-mail/pulse">
                  Insights
</a>              </li>
          </ul>
<span class="sentinel" tabindex="0" aria-hidden="true"></span></details-menu>
</details></div>
</nav>

  </div>

  



<turbo-frame id="repo-content-turbo-frame" target="_top" data-turbo-action="advance" class="">
    <div id="repo-content-pjax-container" class="repository-content ">
      <a href="https://github.dev/" class="d-none js-github-dev-shortcut" data-hotkey=".">Open in github.dev</a>
  <a href="https://github.dev/" class="d-none js-github-dev-new-tab-shortcut" data-hotkey="Shift+.,Shift+>,>" target="_blank">Open in a new github.dev tab</a>
    <a class="d-none" data-hotkey="," target="_blank" href="/codespaces/new/bbottema/simple-java-mail/tree/master?resume=1">Open in codespace</a>



    
      
  <div class="clearfix container-xl px-3 px-md-4 px-lg-5 mt-4">
    <div class="mb-3">
  <span data-view-component="true" class="Label Label--success">Beta</span>
  <a class="text-small" href="#enroll-beta" data-feature-preview-trigger-url="/users/S230306/feature_previews?selected_slug=code_search_code_view">
     Try the new code view
  </a>
</div>

    
    
<div>
  

  



    
<a class="d-none js-permalink-shortcut" data-hotkey="y" href="/bbottema/simple-java-mail/blob/82f8a1701fad71d203872cbf58ae61c429bd93dd/README.md">Permalink</a>

<div class="d-flex flex-items-start flex-shrink-0 pb-3 flex-wrap flex-md-nowrap flex-justify-between flex-md-justify-start">
  
<div class="position-relative">
  <details class="js-branch-select-menu details-reset details-overlay mr-0 mb-0 " id="branch-select-menu" data-hydro-click-payload="{&quot;event_type&quot;:&quot;repository.click&quot;,&quot;payload&quot;:{&quot;target&quot;:&quot;REFS_SELECTOR_MENU&quot;,&quot;repository_id&quot;:34100441,&quot;originating_url&quot;:&quot;https://github.com/bbottema/simple-java-mail/blob/master/README.md&quot;,&quot;user_id&quot;:99464989}}" data-hydro-click-hmac="c832bced41a82a9723971081031ea68a07ae5f55974d0cb92b33b06dcbaa6425">
    <summary class="btn css-truncate" data-hotkey="w" title="Switch branches or tags">
      <svg text="gray" aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-git-branch">
    <path d="M9.5 3.25a2.25 2.25 0 1 1 3 2.122V6A2.5 2.5 0 0 1 10 8.5H6a1 1 0 0 0-1 1v1.128a2.251 2.251 0 1 1-1.5 0V5.372a2.25 2.25 0 1 1 1.5 0v1.836A2.493 2.493 0 0 1 6 7h4a1 1 0 0 0 1-1v-.628A2.25 2.25 0 0 1 9.5 3.25Zm-6 0a.75.75 0 1 0 1.5 0 .75.75 0 0 0-1.5 0Zm8.25-.75a.75.75 0 1 0 0 1.5.75.75 0 0 0 0-1.5ZM4.25 12a.75.75 0 1 0 0 1.5.75.75 0 0 0 0-1.5Z"></path>
</svg>
      <span class="css-truncate-target" data-menu-button="">master</span>
      <span class="dropdown-caret"></span>
    </summary>

    
<div class="SelectMenu">
  <div class="SelectMenu-modal">
    <header class="SelectMenu-header">
      <span class="SelectMenu-title">Switch branches/tags</span>
      <button class="SelectMenu-closeButton" type="button" data-toggle-for="branch-select-menu"><svg aria-label="Close menu" aria-hidden="false" role="img" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-x">
    <path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path>
</svg></button>
    </header>

    <input-demux data-action="tab-container-change:input-demux#storeInput tab-container-changed:input-demux#updateInput" data-catalyst="">
      <tab-container class="d-flex flex-column js-branches-tags-tabs" style="min-height: 0;">
        <div class="SelectMenu-filter">
          <input data-target="input-demux.source" id="context-commitish-filter-field" class="SelectMenu-input form-control" aria-owns="ref-list-branches" data-controls-ref-menu-id="ref-list-branches" autofocus="" autocomplete="off" aria-label="Filter branches/tags" placeholder="Filter branches/tags" type="text">
        </div>

        <div class="SelectMenu-tabs" role="tablist" data-target="input-demux.control">
          <button class="SelectMenu-tab" type="button" role="tab" aria-selected="true" tabindex="0">Branches</button>
          <button class="SelectMenu-tab" type="button" role="tab" aria-selected="false" tabindex="-1">Tags</button>
        </div>

        <div role="tabpanel" id="ref-list-branches" data-filter-placeholder="Filter branches/tags" tabindex="" class="d-flex flex-column flex-auto overflow-auto">
          <ref-selector type="branch" data-targets="input-demux.sinks" data-action="
              input-entered:ref-selector#inputEntered
              tab-selected:ref-selector#tabSelected
              focus-list:ref-selector#focusFirstListMember
            " query-endpoint="/bbottema/simple-java-mail/refs" cache-key="v0:1681568109.0" current-committish="bWFzdGVy" default-branch="bWFzdGVy" name-with-owner="YmJvdHRlbWEvc2ltcGxlLWphdmEtbWFpbA==" prefetch-on-mouseover="" data-catalyst="">

            <template data-target="ref-selector.fetchFailedTemplate">
              <div class="SelectMenu-message" data-index="{{ index }}">Could not load branches</div>
            </template>

              <template data-target="ref-selector.noMatchTemplate">
    <div class="SelectMenu-message">Nothing to show</div>
</template>


            <div data-target="ref-selector.listContainer" role="menu" class="SelectMenu-list " data-turbo-frame="repo-content-turbo-frame">
              <div class="SelectMenu-loading pt-3 pb-0 overflow-hidden" aria-label="Menu is loading">
                <svg style="box-sizing: content-box; color: var(--color-icon-primary);" width="32" height="32" viewBox="0 0 16 16" fill="none" data-view-component="true" class="anim-rotate">
  <circle cx="8" cy="8" r="7" stroke="currentColor" stroke-opacity="0.25" stroke-width="2" vector-effect="non-scaling-stroke"></circle>
  <path d="M15 8a7.002 7.002 0 00-7-7" stroke="currentColor" stroke-width="2" stroke-linecap="round" vector-effect="non-scaling-stroke"></path>
</svg>
              </div>
            </div>

              

<template data-target="ref-selector.itemTemplate">
  <a href="https://github.com/bbottema/simple-java-mail/blob/{{ urlEncodedRefName }}/README.md" class="SelectMenu-item" role="menuitemradio" rel="nofollow" aria-checked="{{ isCurrent }}" data-index="{{ index }}">
    <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check SelectMenu-icon SelectMenu-icon--check">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    <span class="flex-1 css-truncate css-truncate-overflow {{ isFilteringClass }}">{{ refName }}</span>
    <span hidden="{{ isNotDefault }}" class="Label Label--secondary flex-self-start">default</span>
  </a>
</template>


              <footer class="SelectMenu-footer"><a href="/bbottema/simple-java-mail/branches">View all branches</a></footer>
          </ref-selector>

        </div>

        <div role="tabpanel" id="tags-menu" data-filter-placeholder="Find a tag" tabindex="" hidden="" class="d-flex flex-column flex-auto overflow-auto">
          <ref-selector type="tag" data-action="
              input-entered:ref-selector#inputEntered
              tab-selected:ref-selector#tabSelected
              focus-list:ref-selector#focusFirstListMember
            " data-targets="input-demux.sinks" query-endpoint="/bbottema/simple-java-mail/refs" cache-key="v0:1681568109.0" current-committish="bWFzdGVy" default-branch="bWFzdGVy" name-with-owner="YmJvdHRlbWEvc2ltcGxlLWphdmEtbWFpbA==" data-catalyst="">

            <template data-target="ref-selector.fetchFailedTemplate">
              <div class="SelectMenu-message" data-index="{{ index }}">Could not load tags</div>
            </template>

            <template data-target="ref-selector.noMatchTemplate">
              <div class="SelectMenu-message" data-index="{{ index }}">Nothing to show</div>
            </template>

              

<template data-target="ref-selector.itemTemplate">
  <a href="https://github.com/bbottema/simple-java-mail/blob/{{ urlEncodedRefName }}/README.md" class="SelectMenu-item" role="menuitemradio" rel="nofollow" aria-checked="{{ isCurrent }}" data-index="{{ index }}">
    <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check SelectMenu-icon SelectMenu-icon--check">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    <span class="flex-1 css-truncate css-truncate-overflow {{ isFilteringClass }}">{{ refName }}</span>
    <span hidden="{{ isNotDefault }}" class="Label Label--secondary flex-self-start">default</span>
  </a>
</template>


            <div data-target="ref-selector.listContainer" role="menu" class="SelectMenu-list" data-turbo-frame="repo-content-turbo-frame">
              <div class="SelectMenu-loading pt-3 pb-0 overflow-hidden" aria-label="Menu is loading">
                <svg style="box-sizing: content-box; color: var(--color-icon-primary);" width="32" height="32" viewBox="0 0 16 16" fill="none" data-view-component="true" class="anim-rotate">
  <circle cx="8" cy="8" r="7" stroke="currentColor" stroke-opacity="0.25" stroke-width="2" vector-effect="non-scaling-stroke"></circle>
  <path d="M15 8a7.002 7.002 0 00-7-7" stroke="currentColor" stroke-width="2" stroke-linecap="round" vector-effect="non-scaling-stroke"></path>
</svg>
              </div>
            </div>
              <footer class="SelectMenu-footer"><a href="/bbottema/simple-java-mail/tags">View all tags</a></footer>
          </ref-selector>
        </div>
      </tab-container>
    </input-demux>
  </div>
</div>

  </details>

</div>


<div class="Overlay--hidden Overlay-backdrop--center" data-modal-dialog-overlay="">
  <modal-dialog role="dialog" id="warn-tag-match-create-branch-dialog" aria-modal="true" aria-labelledby="warn-tag-match-create-branch-dialog-header" data-view-component="true" class="Overlay Overlay--width-large Overlay--height-auto Overlay--motion-scaleFade">
      <header class="Overlay-header Overlay-header--large Overlay-header--divided">
        <div class="Overlay-headerContentWrap">
          <div class="Overlay-titleWrap">
            <h1 id="warn-tag-match-create-branch-dialog-header" class="Overlay-title">Name already in use</h1>
          </div>
          <div class="Overlay-actionWrap">
            <button data-close-dialog-id="warn-tag-match-create-branch-dialog" aria-label="Close" type="button" data-view-component="true" class="close-button Overlay-closeButton"><svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-x">
    <path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path>
</svg></button>
          </div>
        </div>
      </header>
    <div class="Overlay-body ">
      
          <div data-view-component="true">      A tag already exists with the provided branch name. Many Git commands accept both tag and branch names, so creating this branch may cause unexpected behavior. Are you sure you want to create this branch?
</div>

    </div>
      <footer class="Overlay-footer Overlay-footer--alignEnd">
            <button data-close-dialog-id="warn-tag-match-create-branch-dialog" type="button" data-view-component="true" class="btn">    Cancel
</button>
            <button data-submit-dialog-id="warn-tag-match-create-branch-dialog" type="button" data-view-component="true" class="btn-danger btn">    Create
</button>
      </footer>
</modal-dialog></div>


  <h2 id="blob-path" class="breadcrumb flex-auto flex-self-center min-width-0 text-normal mx-2 width-full width-md-auto flex-order-1 flex-md-order-none mt-3 mt-md-0">
    <span class="js-repo-root text-bold"><span class="js-path-segment d-inline-block wb-break-all"><a data-turbo-frame="repo-content-turbo-frame" href="/bbottema/simple-java-mail"><span>simple-java-mail</span></a></span></span><span class="separator">/</span><strong class="final-path">README.md</strong>
  </h2>
    <a href="/bbottema/simple-java-mail/find/master" data-pjax="" data-hotkey="t" data-view-component="true" class="btn mr-2 d-none d-md-block">    Go to file
</a>
  <details id="blob-more-options-details" data-view-component="true" class="details-overlay details-reset position-relative">
    <summary role="button" data-view-component="true" class="btn">    <svg aria-label="More options" role="img" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-kebab-horizontal">
    <path d="M8 9a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3ZM1.5 9a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3Zm13 0a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3Z"></path>
</svg>
</summary>
  <div data-view-component="true">      <ul class="dropdown-menu dropdown-menu-sw">
        <li class="d-block d-md-none">
          <a class="dropdown-item d-flex flex-items-baseline" data-hydro-click="{&quot;event_type&quot;:&quot;repository.click&quot;,&quot;payload&quot;:{&quot;target&quot;:&quot;FIND_FILE_BUTTON&quot;,&quot;repository_id&quot;:34100441,&quot;originating_url&quot;:&quot;https://github.com/bbottema/simple-java-mail/blob/master/README.md&quot;,&quot;user_id&quot;:99464989}}" data-hydro-click-hmac="1cbe0d7eec04a8b598a94c5f2db36144bef1f76ccc039a6e713e2cec73150e7c" data-ga-click="Repository, find file, location:repo overview" data-hotkey="t" href="/bbottema/simple-java-mail/find/master">
            <span class="flex-auto">Go to file</span>
            <span class="text-small color-fg-muted" aria-hidden="true">T</span>
</a>        </li>
        <li data-toggle-for="blob-more-options-details">
            <button data-toggle-for="jumpto-line-details-dialog" type="button" data-view-component="true" class="dropdown-item btn-link">    <span class="d-flex flex-items-baseline">
              <span class="flex-auto">Go to line</span>
              <span class="text-small color-fg-muted" aria-hidden="true">L</span>
            </span>
</button>        </li>
        <li class="dropdown-divider" role="none"></li>
        <li>
          <clipboard-copy data-toggle-for="blob-more-options-details" aria-label="Copy path" value="README.md" data-view-component="true" class="dropdown-item cursor-pointer" tabindex="0" role="button">
    
            Copy path

</clipboard-copy>        </li>
        <li>
          <clipboard-copy data-toggle-for="blob-more-options-details" aria-label="Copy permalink" value="https://github.com/bbottema/simple-java-mail/blob/82f8a1701fad71d203872cbf58ae61c429bd93dd/README.md" data-view-component="true" class="dropdown-item cursor-pointer" tabindex="0" role="button">
    
            <span class="d-flex flex-items-baseline">
              <span class="flex-auto">Copy permalink</span>
            </span>

</clipboard-copy>        </li>
      </ul>
</div>
</details></div>





    <div id="spoof-warning" class="mt-0 pb-3" hidden="" aria-hidden="">
  <div data-view-component="true" class="flash flash-warn mt-0 clearfix">
  
    <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-alert float-left mt-1">
    <path d="M6.457 1.047c.659-1.234 2.427-1.234 3.086 0l6.082 11.378A1.75 1.75 0 0 1 14.082 15H1.918a1.75 1.75 0 0 1-1.543-2.575Zm1.763.707a.25.25 0 0 0-.44 0L1.698 13.132a.25.25 0 0 0 .22.368h12.164a.25.25 0 0 0 .22-.368Zm.53 3.996v2.5a.75.75 0 0 1-1.5 0v-2.5a.75.75 0 0 1 1.5 0ZM9 11a1 1 0 1 1-2 0 1 1 0 0 1 2 0Z"></path>
</svg>

      <div class="overflow-hidden">This commit does not belong to any branch on this repository, and may belong to a fork outside of the repository.</div>


  
</div></div>

    



    <div class="Box d-flex flex-column flex-shrink-0 mb-3">
  

  <div class="Box-header Details js-details-container">
      <div class="d-flex flex-items-center">
        <span class="flex-shrink-0 ml-n1 mr-n1 mt-n1 mb-n1">
          <a rel="author" data-hovercard-type="user" data-hovercard-url="/users/bbottema/hovercard" data-octo-click="hovercard-link-click" data-octo-dimensions="link_type:self" href="/bbottema"><img class="avatar avatar-user" src="https://avatars.githubusercontent.com/u/2115718?s=48&amp;v=4" width="24" height="24" alt="@bbottema"></a>
        </span>
        <div class="flex-1 d-flex flex-items-center ml-3 min-width-0">
          <div class="css-truncate css-truncate-overflow">
            <a class="text-bold Link--primary" rel="author" data-hovercard-type="user" data-hovercard-url="/users/bbottema/hovercard" data-octo-click="hovercard-link-click" data-octo-dimensions="link_type:self" href="/bbottema">bbottema</a>

              <span class="markdown-title">
                <a data-pjax="true" title="Preparing release 8.1.0" class="Link--secondary" href="/bbottema/simple-java-mail/commit/7b0e3f589db8a0223c9cb9c34232ba6ad149ae84">Preparing release 8.1.0</a>
              </span>
          </div>


          <span class="ml-2">
            
  <details class="commit-build-statuses details-overlay details-reset js-dropdown-details hx_dropdown-fullscreen js-socket-channel js-updatable-content" data-channel="eyJjIjoicmVwbzozNDEwMDQ0MTpjb21taXQ6N2IwZTNmNTg5ZGI4YTAyMjNjOWNiOWMzNDIzMmJhNmFkMTQ5YWU4NCIsInQiOjE2ODMxMDk5Mjh9--ae57bbe587a87a0600746898729b3da8308d7c020a803e8235aa2fd2bf68b506" data-url="/bbottema/simple-java-mail/commit/7b0e3f589db8a0223c9cb9c34232ba6ad149ae84/rollup" data-deferred-details-content-url="/bbottema/simple-java-mail/commit/7b0e3f589db8a0223c9cb9c34232ba6ad149ae84/status-details?popover=true">
    <summary class="color-fg-danger">
      <svg aria-label="2 / 6 checks OK" role="img" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-x">
    <path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path>
</svg>
    </summary>
    <div class="dropdown-menu status-checks-dropdown dropdown-menu-e overflow-hidden">
      <include-fragment class="m-4 d-flex flex-column flex-items-center">
        <svg style="box-sizing: content-box; color: var(--color-icon-primary);" width="32" height="32" viewBox="0 0 16 16" fill="none" data-view-component="true" class="anim-rotate">
  <circle cx="8" cy="8" r="7" stroke="currentColor" stroke-opacity="0.25" stroke-width="2" vector-effect="non-scaling-stroke"></circle>
  <path d="M15 8a7.002 7.002 0 00-7-7" stroke="currentColor" stroke-width="2" stroke-linecap="round" vector-effect="non-scaling-stroke"></path>
</svg>
        <div class="color-fg-muted no-wrap">Loading status checks…</div>
      </include-fragment>
    </div>
  </details>

          </span>
        </div>
        <div class="ml-3 d-flex flex-shrink-0 flex-items-center flex-justify-end color-fg-muted no-wrap">
          <span class="d-none d-md-inline">
            <span>Latest commit</span>
            <a class="text-small text-mono Link--secondary" href="/bbottema/simple-java-mail/commit/7b0e3f589db8a0223c9cb9c34232ba6ad149ae84" data-pjax="">7b0e3f5</a>
            <span itemprop="dateModified"><relative-time datetime="2023-04-15T13:58:59Z" class="no-wrap" title="Apr 15, 2023, 7:28 PM GMT+5:30">Apr 15, 2023</relative-time></span>
          </span>

          <a data-pjax="" href="/bbottema/simple-java-mail/commits/master/README.md" class="ml-3 no-wrap Link--primary no-underline">
            <svg text="gray" aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-history">
    <path d="m.427 1.927 1.215 1.215a8.002 8.002 0 1 1-1.6 5.685.75.75 0 1 1 1.493-.154 6.5 6.5 0 1 0 1.18-4.458l1.358 1.358A.25.25 0 0 1 3.896 6H.25A.25.25 0 0 1 0 5.75V2.104a.25.25 0 0 1 .427-.177ZM7.75 4a.75.75 0 0 1 .75.75v2.992l2.028.812a.75.75 0 0 1-.557 1.392l-2.5-1A.751.751 0 0 1 7 8.25v-3.5A.75.75 0 0 1 7.75 4Z"></path>
</svg>
            <span class="d-none d-sm-inline">
              <strong>History</strong>
            </span>
          </a>
        </div>
      </div>

  </div>

  <div class="Box-body d-flex flex-items-center flex-auto border-bottom-0 flex-wrap">
    <details class="details-reset details-overlay details-overlay-dark lh-default color-fg-default float-left mr-3" id="blob_contributors_box">
      <summary class="Link--primary" role="button">
        <svg text="gray" aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-people">
    <path d="M2 5.5a3.5 3.5 0 1 1 5.898 2.549 5.508 5.508 0 0 1 3.034 4.084.75.75 0 1 1-1.482.235 4 4 0 0 0-7.9 0 .75.75 0 0 1-1.482-.236A5.507 5.507 0 0 1 3.102 8.05 3.493 3.493 0 0 1 2 5.5ZM11 4a3.001 3.001 0 0 1 2.22 5.018 5.01 5.01 0 0 1 2.56 3.012.749.749 0 0 1-.885.954.752.752 0 0 1-.549-.514 3.507 3.507 0 0 0-2.522-2.372.75.75 0 0 1-.574-.73v-.352a.75.75 0 0 1 .416-.672A1.5 1.5 0 0 0 11 5.5.75.75 0 0 1 11 4Zm-5.5-.5a2 2 0 1 0-.001 3.999A2 2 0 0 0 5.5 3.5Z"></path>
</svg>
        <strong>3</strong>
        
        contributors
      </summary>
      <details-dialog class="Box Box--overlay d-flex flex-column anim-fade-in fast" aria-label="Users who have contributed to this file" src="/bbottema/simple-java-mail/contributors-list/master/README.md" preload="" role="dialog" aria-modal="true">
        <div class="Box-header">
          <button class="Box-btn-octicon btn-octicon float-right" type="button" aria-label="Close dialog" data-close-dialog="">
            <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-x">
    <path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path>
</svg>
          </button>
          <h3 class="Box-title">
            Users who have contributed to this file
          </h3>
        </div>
        <include-fragment>
          <svg style="box-sizing: content-box; color: var(--color-icon-primary);" width="32" height="32" viewBox="0 0 16 16" fill="none" data-view-component="true" class="my-3 mx-auto d-block anim-rotate">
  <circle cx="8" cy="8" r="7" stroke="currentColor" stroke-opacity="0.25" stroke-width="2" vector-effect="non-scaling-stroke"></circle>
  <path d="M15 8a7.002 7.002 0 00-7-7" stroke="currentColor" stroke-width="2" stroke-linecap="round" vector-effect="non-scaling-stroke"></path>
</svg>
        </include-fragment>
      </details-dialog>
    </details>
      <span class="">
    <a class="avatar-link" data-hovercard-type="user" data-hovercard-url="/users/bbottema/hovercard" data-octo-click="hovercard-link-click" data-octo-dimensions="link_type:self" href="/bbottema/simple-java-mail/commits/master/README.md?author=bbottema">
      <img class="avatar mr-2 avatar-user" src="https://avatars.githubusercontent.com/u/2115718?s=48&amp;v=4" width="24" height="24" alt="@bbottema"> 
</a>    <a class="avatar-link" data-hovercard-type="user" data-hovercard-url="/users/koppor/hovercard" data-octo-click="hovercard-link-click" data-octo-dimensions="link_type:self" href="/bbottema/simple-java-mail/commits/master/README.md?author=koppor">
      <img class="avatar mr-2 avatar-user" src="https://avatars.githubusercontent.com/u/1366654?s=48&amp;v=4" width="24" height="24" alt="@koppor"> 
</a>    <a class="avatar-link" data-hovercard-type="user" data-hovercard-url="/users/jhult/hovercard" data-octo-click="hovercard-link-click" data-octo-dimensions="link_type:self" href="/bbottema/simple-java-mail/commits/master/README.md?author=jhult">
      <img class="avatar mr-2 avatar-user" src="https://avatars.githubusercontent.com/u/9849069?s=48&amp;v=4" width="24" height="24" alt="@jhult"> 
</a>
</span>

  </div>
</div>



      








    <readme-toc data-catalyst="">

    <div data-target="readme-toc.content" class="Box mt-3 position-relative">
      
  <div class="Box-header js-blob-header blob-header js-sticky js-position-sticky top-0 p-2 d-flex flex-shrink-0 flex-md-row flex-items-center" style="position: sticky; z-index: 1; top: 0px !important;" data-original-top="0px">

      <details data-target="readme-toc.trigger" data-menu-hydro-click="{&quot;event_type&quot;:&quot;repository_toc_menu.click&quot;,&quot;payload&quot;:{&quot;target&quot;:&quot;trigger&quot;,&quot;repository_id&quot;:34100441,&quot;originating_url&quot;:&quot;https://github.com/bbottema/simple-java-mail/blob/master/README.md&quot;,&quot;user_id&quot;:99464989}}" data-menu-hydro-click-hmac="dd52a028a42f9a9d71a99364499dafde572991591e45ef25b2982137cdf486cd" class="dropdown details-reset details-overlay">
  <summary class="btn btn-octicon m-0 mr-2 p-2" aria-haspopup="menu" aria-label="Table of Contents" role="button">
    <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-list-unordered">
    <path d="M5.75 2.5h8.5a.75.75 0 0 1 0 1.5h-8.5a.75.75 0 0 1 0-1.5Zm0 5h8.5a.75.75 0 0 1 0 1.5h-8.5a.75.75 0 0 1 0-1.5Zm0 5h8.5a.75.75 0 0 1 0 1.5h-8.5a.75.75 0 0 1 0-1.5ZM2 14a1 1 0 1 1 0-2 1 1 0 0 1 0 2Zm1-6a1 1 0 1 1-2 0 1 1 0 0 1 2 0ZM2 4a1 1 0 1 1 0-2 1 1 0 0 1 0 2Z"></path>
</svg>
  </summary>


  <details-menu class="SelectMenu" role="menu" data-focus-trap="suspended"><span class="sentinel" tabindex="0" aria-hidden="true"></span>
    <div class="SelectMenu-modal rounded-3 mt-1" style="max-height:340px;">

        <div class="SelectMenu-filter">
          <input class="SelectMenu-input form-control js-filterable-field" id="toc-filter-field" type="text" autocomplete="off" spellcheck="false" autofocus="" placeholder="Filter headings" aria-label="Filter headings">
        </div>

      <div class="SelectMenu-list SelectMenu-list--borderless p-2" style="overscroll-behavior: contain;" data-filterable-for="toc-filter-field" data-filterable-type="substring">
          <a role="menuitem" class="filter-item SelectMenu-item ws-normal wb-break-word line-clamp-2 py-1 text-emphasized" style="-webkit-box-orient: vertical; padding-left: 12px; background-color: var(--color-accent-emphasis);" data-action="click:readme-toc#blur" data-targets="readme-toc.entries" data-hydro-click="{&quot;event_type&quot;:&quot;repository_toc_menu.click&quot;,&quot;payload&quot;:{&quot;target&quot;:&quot;entry&quot;,&quot;repository_id&quot;:34100441,&quot;originating_url&quot;:&quot;https://github.com/bbottema/simple-java-mail/blob/master/README.md&quot;,&quot;user_id&quot;:99464989}}" data-hydro-click-hmac="58d1bf490af5fcf7a82ed0befa0b4aa53eb2af6a590d95974d5999ffa76fcf78" href="#simple-java-mail" aria-current="page">Simple Java Mail</a>
          <a role="menuitem" class="filter-item SelectMenu-item ws-normal wb-break-word line-clamp-2 py-1 " style="-webkit-box-orient: vertical; padding-left: 36px;" data-action="click:readme-toc#blur" data-targets="readme-toc.entries" data-hydro-click="{&quot;event_type&quot;:&quot;repository_toc_menu.click&quot;,&quot;payload&quot;:{&quot;target&quot;:&quot;entry&quot;,&quot;repository_id&quot;:34100441,&quot;originating_url&quot;:&quot;https://github.com/bbottema/simple-java-mail/blob/master/README.md&quot;,&quot;user_id&quot;:99464989}}" data-hydro-click-hmac="58d1bf490af5fcf7a82ed0befa0b4aa53eb2af6a590d95974d5999ffa76fcf78" href="#simplejavamailorg">simplejavamail.org</a>
          <a role="menuitem" class="filter-item SelectMenu-item ws-normal wb-break-word line-clamp-2 py-1 " style="-webkit-box-orient: vertical; padding-left: 36px;" data-action="click:readme-toc#blur" data-targets="readme-toc.entries" data-hydro-click="{&quot;event_type&quot;:&quot;repository_toc_menu.click&quot;,&quot;payload&quot;:{&quot;target&quot;:&quot;entry&quot;,&quot;repository_id&quot;:34100441,&quot;originating_url&quot;:&quot;https://github.com/bbottema/simple-java-mail/blob/master/README.md&quot;,&quot;user_id&quot;:99464989}}" data-hydro-click-hmac="58d1bf490af5fcf7a82ed0befa0b4aa53eb2af6a590d95974d5999ffa76fcf78" href="#latest-progress">Latest Progress</a>
          <a role="menuitem" class="filter-item SelectMenu-item ws-normal wb-break-word line-clamp-2 py-1 " style="-webkit-box-orient: vertical; padding-left: 48px;" data-action="click:readme-toc#blur" data-targets="readme-toc.entries" data-hydro-click="{&quot;event_type&quot;:&quot;repository_toc_menu.click&quot;,&quot;payload&quot;:{&quot;target&quot;:&quot;entry&quot;,&quot;repository_id&quot;:34100441,&quot;originating_url&quot;:&quot;https://github.com/bbottema/simple-java-mail/blob/master/README.md&quot;,&quot;user_id&quot;:99464989}}" data-hydro-click-hmac="58d1bf490af5fcf7a82ed0befa0b4aa53eb2af6a590d95974d5999ffa76fcf78" href="#whats-new">What's new</a>
          <a role="menuitem" class="filter-item SelectMenu-item ws-normal wb-break-word line-clamp-2 py-1 " style="-webkit-box-orient: vertical; padding-left: 48px;" data-action="click:readme-toc#blur" data-targets="readme-toc.entries" data-hydro-click="{&quot;event_type&quot;:&quot;repository_toc_menu.click&quot;,&quot;payload&quot;:{&quot;target&quot;:&quot;entry&quot;,&quot;repository_id&quot;:34100441,&quot;originating_url&quot;:&quot;https://github.com/bbottema/simple-java-mail/blob/master/README.md&quot;,&quot;user_id&quot;:99464989}}" data-hydro-click-hmac="58d1bf490af5fcf7a82ed0befa0b4aa53eb2af6a590d95974d5999ffa76fcf78" href="#about-the-migration">About the migration</a>
          <a role="menuitem" class="filter-item SelectMenu-item ws-normal wb-break-word line-clamp-2 py-1 " style="-webkit-box-orient: vertical; padding-left: 48px;" data-action="click:readme-toc#blur" data-targets="readme-toc.entries" data-hydro-click="{&quot;event_type&quot;:&quot;repository_toc_menu.click&quot;,&quot;payload&quot;:{&quot;target&quot;:&quot;entry&quot;,&quot;repository_id&quot;:34100441,&quot;originating_url&quot;:&quot;https://github.com/bbottema/simple-java-mail/blob/master/README.md&quot;,&quot;user_id&quot;:99464989}}" data-hydro-click-hmac="58d1bf490af5fcf7a82ed0befa0b4aa53eb2af6a590d95974d5999ffa76fcf78" href="#new-features-and-enhancements">New features and enhancements</a>
          <a role="menuitem" class="filter-item SelectMenu-item ws-normal wb-break-word line-clamp-2 py-1 " style="-webkit-box-orient: vertical; padding-left: 48px;" data-action="click:readme-toc#blur" data-targets="readme-toc.entries" data-hydro-click="{&quot;event_type&quot;:&quot;repository_toc_menu.click&quot;,&quot;payload&quot;:{&quot;target&quot;:&quot;entry&quot;,&quot;repository_id&quot;:34100441,&quot;originating_url&quot;:&quot;https://github.com/bbottema/simple-java-mail/blob/master/README.md&quot;,&quot;user_id&quot;:99464989}}" data-hydro-click-hmac="58d1bf490af5fcf7a82ed0befa0b4aa53eb2af6a590d95974d5999ffa76fcf78" href="#bugs-solved">Bugs solved</a>
          <a role="menuitem" class="filter-item SelectMenu-item ws-normal wb-break-word line-clamp-2 py-1 " style="-webkit-box-orient: vertical; padding-left: 48px;" data-action="click:readme-toc#blur" data-targets="readme-toc.entries" data-hydro-click="{&quot;event_type&quot;:&quot;repository_toc_menu.click&quot;,&quot;payload&quot;:{&quot;target&quot;:&quot;entry&quot;,&quot;repository_id&quot;:34100441,&quot;originating_url&quot;:&quot;https://github.com/bbottema/simple-java-mail/blob/master/README.md&quot;,&quot;user_id&quot;:99464989}}" data-hydro-click-hmac="58d1bf490af5fcf7a82ed0befa0b4aa53eb2af6a590d95974d5999ffa76fcf78" href="#maintenance-updates">Maintenance updates</a>
          <a role="menuitem" class="filter-item SelectMenu-item ws-normal wb-break-word line-clamp-2 py-1 " style="-webkit-box-orient: vertical; padding-left: 48px;" data-action="click:readme-toc#blur" data-targets="readme-toc.entries" data-hydro-click="{&quot;event_type&quot;:&quot;repository_toc_menu.click&quot;,&quot;payload&quot;:{&quot;target&quot;:&quot;entry&quot;,&quot;repository_id&quot;:34100441,&quot;originating_url&quot;:&quot;https://github.com/bbottema/simple-java-mail/blob/master/README.md&quot;,&quot;user_id&quot;:99464989}}" data-hydro-click-hmac="58d1bf490af5fcf7a82ed0befa0b4aa53eb2af6a590d95974d5999ffa76fcf78" href="#included-changes-from-outlook-message-parser">Included changes from outlook-message-parser</a>
          <a role="menuitem" class="filter-item SelectMenu-item ws-normal wb-break-word line-clamp-2 py-1 " style="-webkit-box-orient: vertical; padding-left: 48px;" data-action="click:readme-toc#blur" data-targets="readme-toc.entries" data-hydro-click="{&quot;event_type&quot;:&quot;repository_toc_menu.click&quot;,&quot;payload&quot;:{&quot;target&quot;:&quot;entry&quot;,&quot;repository_id&quot;:34100441,&quot;originating_url&quot;:&quot;https://github.com/bbottema/simple-java-mail/blob/master/README.md&quot;,&quot;user_id&quot;:99464989}}" data-hydro-click-hmac="58d1bf490af5fcf7a82ed0befa0b4aa53eb2af6a590d95974d5999ffa76fcf78" href="#new-features">New features</a>
          <a role="menuitem" class="filter-item SelectMenu-item ws-normal wb-break-word line-clamp-2 py-1 " style="-webkit-box-orient: vertical; padding-left: 48px;" data-action="click:readme-toc#blur" data-targets="readme-toc.entries" data-hydro-click="{&quot;event_type&quot;:&quot;repository_toc_menu.click&quot;,&quot;payload&quot;:{&quot;target&quot;:&quot;entry&quot;,&quot;repository_id&quot;:34100441,&quot;originating_url&quot;:&quot;https://github.com/bbottema/simple-java-mail/blob/master/README.md&quot;,&quot;user_id&quot;:99464989}}" data-hydro-click-hmac="58d1bf490af5fcf7a82ed0befa0b4aa53eb2af6a590d95974d5999ffa76fcf78" href="#security-updates">Security updates</a>
          <a role="menuitem" class="filter-item SelectMenu-item ws-normal wb-break-word line-clamp-2 py-1 " style="-webkit-box-orient: vertical; padding-left: 48px;" data-action="click:readme-toc#blur" data-targets="readme-toc.entries" data-hydro-click="{&quot;event_type&quot;:&quot;repository_toc_menu.click&quot;,&quot;payload&quot;:{&quot;target&quot;:&quot;entry&quot;,&quot;repository_id&quot;:34100441,&quot;originating_url&quot;:&quot;https://github.com/bbottema/simple-java-mail/blob/master/README.md&quot;,&quot;user_id&quot;:99464989}}" data-hydro-click-hmac="58d1bf490af5fcf7a82ed0befa0b4aa53eb2af6a590d95974d5999ffa76fcf78" href="#maintenance-updates-1">Maintenance updates</a>
          <a role="menuitem" class="filter-item SelectMenu-item ws-normal wb-break-word line-clamp-2 py-1 " style="-webkit-box-orient: vertical; padding-left: 48px;" data-action="click:readme-toc#blur" data-targets="readme-toc.entries" data-hydro-click="{&quot;event_type&quot;:&quot;repository_toc_menu.click&quot;,&quot;payload&quot;:{&quot;target&quot;:&quot;entry&quot;,&quot;repository_id&quot;:34100441,&quot;originating_url&quot;:&quot;https://github.com/bbottema/simple-java-mail/blob/master/README.md&quot;,&quot;user_id&quot;:99464989}}" data-hydro-click-hmac="58d1bf490af5fcf7a82ed0befa0b4aa53eb2af6a590d95974d5999ffa76fcf78" href="#bugfixes">Bugfixes</a>
      </div>
    </div>
  <span class="sentinel" tabindex="0" aria-hidden="true"></span></details-menu>
</details>


  <div class="text-mono f6 flex-auto pr-3 flex-order-2 flex-md-order-1">

      669 lines (426 sloc)
      <span class="file-info-divider"></span>
    58.3 KB
  </div>

  <div class="d-flex py-1 py-md-0 flex-auto flex-order-1 flex-md-order-2 flex-sm-grow-0 flex-justify-between hide-sm hide-md">
        <div class="BtnGroup">
      <a href="/bbottema/simple-java-mail/blob/master/README.md?plain=1" data-permalink-href="/bbottema/simple-java-mail/blob/82f8a1701fad71d203872cbf58ae61c429bd93dd/README.md?plain=1" aria-label="Display the source blob" data-view-component="true" class="source tooltipped tooltipped-n js-permalink-replaceable-link btn-sm btn BtnGroup-item">    <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-code">
    <path d="m11.28 3.22 4.25 4.25a.75.75 0 0 1 0 1.06l-4.25 4.25a.749.749 0 0 1-1.275-.326.749.749 0 0 1 .215-.734L13.94 8l-3.72-3.72a.749.749 0 0 1 .326-1.275.749.749 0 0 1 .734.215Zm-6.56 0a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042L2.06 8l3.72 3.72a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L.47 8.53a.75.75 0 0 1 0-1.06Z"></path>
</svg>
</a>      <a href="/bbottema/simple-java-mail/blob/master/README.md" data-permalink-href="/bbottema/simple-java-mail/blob/82f8a1701fad71d203872cbf58ae61c429bd93dd/README.md" aria-label="Display the rendered blob" data-view-component="true" class="rendered tooltipped tooltipped-n selected js-permalink-replaceable-link btn-sm btn BtnGroup-item">    <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-file">
    <path d="M2 1.75C2 .784 2.784 0 3.75 0h6.586c.464 0 .909.184 1.237.513l2.914 2.914c.329.328.513.773.513 1.237v9.586A1.75 1.75 0 0 1 13.25 16h-9.5A1.75 1.75 0 0 1 2 14.25Zm1.75-.25a.25.25 0 0 0-.25.25v12.5c0 .138.112.25.25.25h9.5a.25.25 0 0 0 .25-.25V6h-2.75A1.75 1.75 0 0 1 9 4.25V1.5Zm6.75.062V4.25c0 .138.112.25.25.25h2.688l-.011-.013-2.914-2.914-.013-.011Z"></path>
</svg>
</a>  </div>


    <div class="BtnGroup">
        <a data-permalink-href="/bbottema/simple-java-mail/raw/82f8a1701fad71d203872cbf58ae61c429bd93dd/README.md" href="/bbottema/simple-java-mail/raw/master/README.md" id="raw-url" group_item="true" data-view-component="true" class="js-permalink-replaceable-link Button--secondary Button--small Button">    <span class="Button-content">
      <span class="Button-label">Raw</span>
    </span>
</a>  
          <a data-permalink-href="/bbottema/simple-java-mail/blame/82f8a1701fad71d203872cbf58ae61c429bd93dd/README.md" href="/bbottema/simple-java-mail/blame/master/README.md" group_item="true" data-hotkey="b" data-view-component="true" class="js-update-url-with-hash js-permalink-replaceable-link Button--secondary Button--small Button">    <span class="Button-content">
      <span class="Button-label">Blame</span>
    </span>
</a>  
    </div>

    <div class="d-flex">
        
<div class="ml-1">
  <!-- '"` --><!-- </textarea></xmp> --><form class="BtnGroup-parent js-update-url-with-hash " data-turbo="false" action="/bbottema/simple-java-mail/edit/master/README.md" accept-charset="UTF-8" method="post"><input type="hidden" name="authenticity_token" value="lnaNhVcwiWRNhLwKmPfyHYnG4-WM4RuXCoKGBg4eMpsj78V1Gicmj72FpQZdtTh63bwvKnEdPJhvOuc-qk4IvQ" autocomplete="off">
      <button title="Fork this repository and edit the file" data-hotkey="e" data-disable-with="" type="submit" data-view-component="true" class="btn-sm BtnGroup-item btn">    <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-pencil">
    <path d="M11.013 1.427a1.75 1.75 0 0 1 2.474 0l1.086 1.086a1.75 1.75 0 0 1 0 2.474l-8.61 8.61c-.21.21-.47.364-.756.445l-3.251.93a.75.75 0 0 1-.927-.928l.929-3.25c.081-.286.235-.547.445-.758l8.61-8.61Zm.176 4.823L9.75 4.81l-6.286 6.287a.253.253 0 0 0-.064.108l-.558 1.953 1.953-.558a.253.253 0 0 0 .108-.064Zm1.238-3.763a.25.25 0 0 0-.354 0L10.811 3.75l1.439 1.44 1.263-1.263a.25.25 0 0 0 0-.354Z"></path>
</svg>
</button></form>
  <details class="details-reset details-overlay select-menu BtnGroup-parent d-inline-block position-relative">
      <summary data-disable-invalid="" data-disable-with="" data-dropdown-tracking="{&quot;type&quot;:&quot;blob_edit_dropdown.more_options_click&quot;,&quot;context&quot;:{&quot;repository_id&quot;:34100441,&quot;actor_id&quot;:99464989,&quot;github_dev_enabled&quot;:true,&quot;edit_enabled&quot;:true,&quot;small_screen&quot;:false}}" aria-label="Select additional options" data-view-component="true" class="js-blob-dropdown-click select-menu-button btn-sm btn BtnGroup-item float-none px-2">
</summary>    <div class="SelectMenu right-0">
      <div class="SelectMenu-modal width-full">
        <div class="SelectMenu-list SelectMenu-list--borderless py-2">
          <!-- '"` --><!-- </textarea></xmp> --><form class="SelectMenu-item js-update-url-with-hash " data-turbo="false" action="/bbottema/simple-java-mail/edit/master/README.md" accept-charset="UTF-8" method="post"><input type="hidden" name="authenticity_token" value="oLpz8fCiRP1UcvDkOZhovgLorGR-ImVZjyRhb5Y9yhUVIzsBvbXrFqRz6ej82qLZVpJgq4PeQlbqnABXMm3wMw" autocomplete="off">
              <button title="Fork this repository and edit the file" type="submit" data-view-component="true" class="btn-invisible btn width-full d-flex flex-justify-between color-fg-default text-normal p-0">    <div class="mr-5">Edit this file</div>
              <div class="color-fg-muted">E</div>
</button></form>
            <a aria-label="Open this file in github.dev" data-dropdown-tracking="{&quot;type&quot;:&quot;blob_edit_dropdown.dev_link_click&quot;,&quot;context&quot;:{&quot;repository_id&quot;:34100441,&quot;actor_id&quot;:99464989,&quot;edit_enabled&quot;:true,&quot;small_screen&quot;:false}}" href="https://github.dev/" data-view-component="true" class="SelectMenu-item js-github-dev-shortcut js-blob-dropdown-click width-full d-flex flex-justify-between color-fg-default f5 text-normal">
              <div class="mr-5 no-wrap">Open in github.dev</div>
              <div class="color-fg-muted">.</div>
</a>
            <a data-platforms="windows,mac" aria-label="Open this file in GitHub Desktop" href="https://desktop.github.com" data-view-component="true" class="SelectMenu-item no-wrap js-remove-unless-platform width-full text-normal color-fg-default f5">
              Open in GitHub Desktop
</a>        </div>
      </div>
    </div>
  </details>
</div>


        
<div>
  <remote-clipboard-copy class="d-inline-block btn-octicon" style="height: 26px" data-src="/bbottema/simple-java-mail/raw/82f8a1701fad71d203872cbf58ae61c429bd93dd/README.md" data-action="click:remote-clipboard-copy#remoteCopy" data-state-timeout="2000" data-catalyst="">
  

  <span data-target="remote-clipboard-copy.idle">      <span class="tooltipped tooltipped-nw cursor-pointer" data-hydro-click="{&quot;event_type&quot;:&quot;repository.click&quot;,&quot;payload&quot;:{&quot;target&quot;:&quot;COPY_RAW_CONTENTS_BUTTON&quot;,&quot;repository_id&quot;:34100441,&quot;originating_url&quot;:&quot;https://github.com/bbottema/simple-java-mail/blob/master/README.md&quot;,&quot;user_id&quot;:99464989}}" data-hydro-click-hmac="533064561a11772a20f3d70c62e9e97e43ff408f7dc98813c7a213f6a250a81f" aria-label="Copy raw contents">
        <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
</span></span>
  <span data-target="remote-clipboard-copy.fetching" hidden="">      <svg style="box-sizing: content-box; color: var(--color-icon-primary);" width="16" height="16" viewBox="0 0 16 16" fill="none" data-view-component="true" class="anim-rotate">
  <circle cx="8" cy="8" r="7" stroke="currentColor" stroke-opacity="0.25" stroke-width="2" vector-effect="non-scaling-stroke"></circle>
  <path d="M15 8a7.002 7.002 0 00-7-7" stroke="currentColor" stroke-width="2" stroke-linecap="round" vector-effect="non-scaling-stroke"></path>
</svg>
</span>
  <span data-target="remote-clipboard-copy.success" hidden="">      <span class="tooltipped tooltipped-nw" aria-label="Copied!">
        <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check color-fg-success">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
      </span>
</span>
  <span data-target="remote-clipboard-copy.error" hidden="">      <span class="tooltipped tooltipped-nw" aria-label="Something went wrong. Try again.">
        <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-alert color-fg-attention">
    <path d="M6.457 1.047c.659-1.234 2.427-1.234 3.086 0l6.082 11.378A1.75 1.75 0 0 1 14.082 15H1.918a1.75 1.75 0 0 1-1.543-2.575Zm1.763.707a.25.25 0 0 0-.44 0L1.698 13.132a.25.25 0 0 0 .22.368h12.164a.25.25 0 0 0 .22-.368Zm.53 3.996v2.5a.75.75 0 0 1-1.5 0v-2.5a.75.75 0 0 1 1.5 0ZM9 11a1 1 0 1 1-2 0 1 1 0 0 1 2 0Z"></path>
</svg>
      </span>
</span>
</remote-clipboard-copy></div>


          <!-- '"` --><!-- </textarea></xmp> --><form class="inline-form" data-turbo="false" action="/bbottema/simple-java-mail/delete/master/README.md" accept-charset="UTF-8" method="post"><input type="hidden" name="authenticity_token" value="jWMXZPRYBlJuYV0NaAbm0Fdm6TWzXJFHNXmbn7xmIpe4cgwTCq4NDhg8wxhHw7F1ZqXy-lkzqpehlZGPt_BNag">
            <button class="btn-octicon btn-octicon-danger tooltipped tooltipped-nw" type="submit" aria-label="Fork this repository and delete the file" data-disable-with="">
              <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-trash">
    <path d="M11 1.75V3h2.25a.75.75 0 0 1 0 1.5H2.75a.75.75 0 0 1 0-1.5H5V1.75C5 .784 5.784 0 6.75 0h2.5C10.216 0 11 .784 11 1.75ZM4.496 6.675l.66 6.6a.25.25 0 0 0 .249.225h5.19a.25.25 0 0 0 .249-.225l.66-6.6a.75.75 0 0 1 1.492.149l-.66 6.6A1.748 1.748 0 0 1 10.595 15h-5.19a1.75 1.75 0 0 1-1.741-1.575l-.66-6.6a.75.75 0 1 1 1.492-.15ZM6.5 1.75V3h3V1.75a.25.25 0 0 0-.25-.25h-2.5a.25.25 0 0 0-.25.25Z"></path>
</svg>
            </button>
</form>    </div>
  </div>

    <div class="d-flex hide-lg hide-xl flex-order-2 flex-grow-0">
      <details class="dropdown details-reset details-overlay d-inline-block">
        <summary class="js-blob-dropdown-click btn-octicon p-2" aria-haspopup="true" aria-label="Possible actions" data-dropdown-tracking="{&quot;type&quot;:&quot;blob_edit_dropdown.more_options_click&quot;,&quot;context&quot;:{&quot;repository_id&quot;:34100441,&quot;actor_id&quot;:99464989,&quot;github_dev_enabled&quot;:true,&quot;edit_enabled&quot;:true,&quot;small_screen&quot;:true}}">
          <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-kebab-horizontal">
    <path d="M8 9a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3ZM1.5 9a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3Zm13 0a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3Z"></path>
</svg>
        </summary>

        <ul class="dropdown-menu dropdown-menu-sw" style="width: 175px">
            <li>
                <a class="dropdown-item tooltipped tooltipped-nw js-remove-unless-platform" data-platforms="windows,mac" href="https://desktop.github.com">
                  Open with Desktop
                </a>
            </li>
          <li>
            <a class="dropdown-item" href="/bbottema/simple-java-mail/raw/master/README.md">
              View raw
            </a>
          </li>
            <li>
              <remote-clipboard-copy class="dropdown-item" data-src="/bbottema/simple-java-mail/raw/master/README.md" data-action="click:remote-clipboard-copy#remoteCopy" data-state-timeout="2000" data-catalyst="">
  

  <span data-target="remote-clipboard-copy.idle">                  <span class="cursor-pointer" data-hydro-click="{&quot;event_type&quot;:&quot;repository.click&quot;,&quot;payload&quot;:{&quot;target&quot;:&quot;COPY_RAW_CONTENTS_BUTTON&quot;,&quot;repository_id&quot;:34100441,&quot;originating_url&quot;:&quot;https://github.com/bbottema/simple-java-mail/blob/master/README.md&quot;,&quot;user_id&quot;:99464989}}" data-hydro-click-hmac="533064561a11772a20f3d70c62e9e97e43ff408f7dc98813c7a213f6a250a81f">
                    Copy raw contents
</span></span>
  <span data-target="remote-clipboard-copy.fetching" hidden="">                  Copy raw contents
                  <span class="d-inline-block position-relative" style="top: 3px">
                    <svg aria-label="fetching contents…" style="box-sizing: content-box; color: var(--color-icon-primary);" width="16" height="16" viewBox="0 0 16 16" fill="none" data-view-component="true" class="anim-rotate">
  <circle cx="8" cy="8" r="7" stroke="currentColor" stroke-opacity="0.25" stroke-width="2" vector-effect="non-scaling-stroke"></circle>
  <path d="M15 8a7.002 7.002 0 00-7-7" stroke="currentColor" stroke-width="2" stroke-linecap="round" vector-effect="non-scaling-stroke"></path>
</svg>
                  </span>
</span>
  <span data-target="remote-clipboard-copy.success" hidden="">                  Copy raw contents
                  <svg aria-label="Copied!" role="img" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check color-fg-success">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
</span>
  <span data-target="remote-clipboard-copy.error" hidden="">                  Copy raw contents
                  <svg aria-label="Something went wrong. Try again." role="img" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-alert color-fg-attention">
    <path d="M6.457 1.047c.659-1.234 2.427-1.234 3.086 0l6.082 11.378A1.75 1.75 0 0 1 14.082 15H1.918a1.75 1.75 0 0 1-1.543-2.575Zm1.763.707a.25.25 0 0 0-.44 0L1.698 13.132a.25.25 0 0 0 .22.368h12.164a.25.25 0 0 0 .22-.368Zm.53 3.996v2.5a.75.75 0 0 1-1.5 0v-2.5a.75.75 0 0 1 1.5 0ZM9 11a1 1 0 1 1-2 0 1 1 0 0 1 2 0Z"></path>
</svg>
</span>
</remote-clipboard-copy>            </li>
            <li>
              <a class="dropdown-item" href="/bbottema/simple-java-mail/blame/master/README.md">
                View blame
              </a>
            </li>

              <li class="dropdown-divider" role="none"></li>
              <li>
                <a class="dropdown-item" href="/bbottema/simple-java-mail/edit/master/README.md">Edit file</a>
              </li>
                <li>
                  <a data-dropdown-tracking="{&quot;type&quot;:&quot;blob_edit_dropdown.dev_link_click&quot;,&quot;context&quot;:{&quot;repository_id&quot;:34100441,&quot;actor_id&quot;:99464989,&quot;edit_enabled&quot;:true,&quot;small_screen&quot;:true}}" href="https://github.dev/" data-view-component="true" class="dropdown-item js-github-dev-shortcut js-blob-dropdown-click">Open with github.dev</a>
                </li>
              <li>
                <a class="dropdown-item menu-item-danger" href="/bbottema/simple-java-mail/delete/master/README.md">Delete file</a>
              </li>
        </ul>
      </details>
    </div>
</div>


        <div id="readme" class="Box-body readme blob js-code-block-container p-5 p-xl-6 gist-border-0">
    <article class="markdown-body entry-content container-lg" itemprop="text"><p dir="auto"><a href="/bbottema/simple-java-mail/blob/master/modules/simple-java-mail/LICENSE-2.0.txt"><img src="https://camo.githubusercontent.com/249925a9497567220ac96d095886466924c35dfff03e11ffc07ee0b2378b0873/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f6c6963656e73652d61706163686576322d626c75652e7376673f7374796c653d666c6174" alt="APACHE v2 License" data-canonical-src="https://img.shields.io/badge/license-apachev2-blue.svg?style=flat" style="max-width: 100%;"></a>
<a href="https://search.maven.org/#search%7Cgav%7C1%7Cg%3A%22org.simplejavamail%22%20AND%20v%3A%228.1.0%22" rel="nofollow"><img src="https://camo.githubusercontent.com/4280cf5c648d1be782046bb47a815d6bae3d63a0c7f806b2d6f9d0a110d87348/68747470733a2f2f696d672e736869656c64732e696f2f6d6176656e2d63656e7472616c2f762f6f72672e73696d706c656a6176616d61696c2f73696d706c652d6a6176612d6d61696c2e7376673f7374796c653d666c6174" alt="Latest Release" data-canonical-src="https://img.shields.io/maven-central/v/org.simplejavamail/simple-java-mail.svg?style=flat" style="max-width: 100%;"></a>
<a href="https://www.javadoc.io/doc/org.simplejavamail/maven-master-project" rel="nofollow"><img src="https://camo.githubusercontent.com/0e33fa48fcd4cf39ca9c634ca47df753350cda718cd90b9976b1c176efe13d2d/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f6a617661646f632d382e312e302d627269676874677265656e2e7376673f636f6c6f723d627269676874677265656e" alt="Javadocs" data-canonical-src="https://img.shields.io/badge/javadoc-8.1.0-brightgreen.svg?color=brightgreen" style="max-width: 100%;"></a>
<a href="https://app.codacy.com/gh/bbottema/simple-java-mail" rel="nofollow"><img src="https://camo.githubusercontent.com/f74bae72d91748476c0f37d04498a43b3515c08c507db807c97cf65ee9139fed/68747470733a2f2f696d672e736869656c64732e696f2f636f646163792f67726164652f63373530363636336134616234316534396239363735643837636439303062372e7376673f7374796c653d666c6174" alt="Codacy" data-canonical-src="https://img.shields.io/codacy/grade/c7506663a4ab41e49b9675d87cd900b7.svg?style=flat" style="max-width: 100%;"></a>
<a target="_blank" rel="noopener noreferrer nofollow" href="https://camo.githubusercontent.com/59d5af85ac248b91592670645fdbc7a063a3dcb217a19259c39ce5d2efe377ce/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f6a6176612d312e382b2d6c69676874677261792e737667"><img src="https://camo.githubusercontent.com/59d5af85ac248b91592670645fdbc7a063a3dcb217a19259c39ce5d2efe377ce/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f6a6176612d312e382b2d6c69676874677261792e737667" alt="Java 1.7+" data-canonical-src="https://img.shields.io/badge/java-1.8+-lightgray.svg" style="max-width: 100%;"></a></p>
<h1 dir="auto"><a id="user-content-simple-java-mail" class="anchor" aria-hidden="true" href="#simple-java-mail"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a>Simple Java Mail</h1>
<p dir="auto">Simple Java Mail is the simplest to use lightweight mailing library for Java, while being able to send complex emails including <strong><a href="https://www.simplejavamail.org/cli.html#navigation" rel="nofollow">CLI support</a></strong>, <strong><a href="https://www.simplejavamail.org/features.html#section-proxy" rel="nofollow">authenticated socks proxy</a></strong>(!), <strong><a href="https://www.simplejavamail.org/features.html#section-attachments" rel="nofollow">attachments</a></strong>, <strong><a href="https://www.simplejavamail.org/features.html#section-embedding" rel="nofollow">embedded images</a></strong>, <strong><a href="https://www.simplejavamail.org/features.html#section-custom-headers" rel="nofollow">custom headers and properties</a></strong>, <strong><a href="https://www.simplejavamail.org/features.html#section-email-validation" rel="nofollow">robust address validation</a></strong>, <strong><a href="https://www.simplejavamail.org/features.html#section-builder-api" rel="nofollow">build pattern</a></strong> and even <strong><a href="https://www.simplejavamail.org/features.html#section-dkim" rel="nofollow">DKIM signing</a></strong>, <strong><a href="https://www.simplejavamail.org/features.html#section-sending-smime" rel="nofollow">S/MIME support</a></strong> and <strong><a href="https://www.simplejavamail.org/configuration.html#section-config-properties" rel="nofollow">external configuration files</a></strong> with <strong>property overriding</strong>, <strong><a href="https://www.simplejavamail.org/configuration.html#section-spring-support" rel="nofollow">Spring support</a></strong> and <strong><a href="https://www.simplejavamail.org/features.html#section-converting" rel="nofollow">Email conversion</a></strong> tools. Just send your emails without dealing with <a href="https://www.simplejavamail.org/rfc-compliant.html#navigation" rel="nofollow">RFCs</a>.</p>
<p dir="auto">The Simple Java Mail library is a thin layer on top of <a href="https://eclipse-ee4j.github.io/mail/" rel="nofollow">Jakarta Mail</a> that allows users to define emails on a high abstraction level without having to deal with mumbo jumbo such as 'multipart' and 'mimemessage'.</p>
<h3 dir="auto"><a id="user-content-simplejavamailorg" class="anchor" aria-hidden="true" href="#simplejavamailorg"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><a href="https://www.simplejavamail.org" rel="nofollow">simplejavamail.org</a></h3>
<p dir="auto">Simple Java Mail is also available in <a href="https://search.maven.org/#search%7Cgav%7C1%7Cg%3A%22org.simplejavamail%22%20AND%20a%3A%22simple-java-mail%22" rel="nofollow">Maven Central</a>:</p>
<div class="highlight highlight-text-xml notranslate position-relative overflow-auto" dir="auto"><pre>&lt;<span class="pl-ent">dependency</span>&gt;
    &lt;<span class="pl-ent">groupId</span>&gt;org.simplejavamail&lt;/<span class="pl-ent">groupId</span>&gt;
    &lt;<span class="pl-ent">artifactId</span>&gt;simple-java-mail&lt;/<span class="pl-ent">artifactId</span>&gt;
    &lt;<span class="pl-ent">version</span>&gt;8.1.0&lt;/<span class="pl-ent">version</span>&gt;
&lt;/<span class="pl-ent">dependency</span>&gt;</pre><div class="zeroclipboard-container position-absolute right-0 top-0">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn js-clipboard-copy m-2 p-0 tooltipped-no-delay" data-copy-feedback="Copied!" data-tooltip-direction="w" value="<dependency>
    <groupId>org.simplejavamail</groupId>
    <artifactId>simple-java-mail</artifactId>
    <version>8.1.0</version>
</dependency>" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon m-2">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none m-2">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<h3 dir="auto"><a id="user-content-latest-progress" class="anchor" aria-hidden="true" href="#latest-progress"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a>Latest Progress</h3>
<p dir="auto"><a href="https://repo1.maven.org/maven2/org/simplejavamail/simple-java-mail/8.1.0/" rel="nofollow">v8.1.0</a> (15-April-2023)</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/pull/458" data-hovercard-type="pull_request" data-hovercard-url="/bbottema/simple-java-mail/pull/458/hovercard">#458</a> Missing osgi headers (#288) and added support for Apache Karaf</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/288" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/288/hovercard">#288</a> Maintenance: missing OSGI package-exports from core-module</li>
</ul>
<p dir="auto">v8.0.0 - <a href="https://repo1.maven.org/maven2/org/simplejavamail/simple-java-mail/8.0.1/" rel="nofollow">v8.0.1</a></p>
<ul dir="auto">
<li>v8.0.1 (30-April-2023): <a href="https://github.com/bbottema/simple-java-mail/issues/456" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/456/hovercard">#456</a>: Enhancement: make Content-Transfer encoder detection more lenient, supporting more values from the wild</li>
<li>v8.0.0 (08-March-2023): <a href="https://github.com/bbottema/simple-java-mail/issues/451" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/451/hovercard">#451</a>: Feature: Make defaults and overrides a first class feature</li>
<li>v8.0.0 (08-March-2023): <a href="https://github.com/bbottema/simple-java-mail/issues/452" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/452/hovercard">#452</a>: Enhancement: with ".disableAllClientValidation(true)", also ignore errors from the completeness check</li>
<li>v8.0.0 (08-March-2023): <a href="https://github.com/bbottema/simple-java-mail/issues/450" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/450/hovercard">#450</a>: Bug: when using dispositionNotificationTo or returnReceiptTo mode, when the corresponding emails are not filled, it fails even though it should fall back to replyTo or From</li>
<li>v8.0.0 (08-March-2023): <a href="https://github.com/bbottema/simple-java-mail/issues/449" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/449/hovercard">#449</a>: Bug: IllegalArgumentException on parsing empty header name and value (when parsing Outlook message)</li>
<li>v8.0.0 (08-March-2023): <a href="https://github.com/bbottema/simple-java-mail/issues/448" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/448/hovercard">#448</a>: Bug: withEmailDefaults and withEmailOverrides does not work with CustomMailer</li>
<li>v8.0.0 (08-March-2023): <a href="https://github.com/bbottema/simple-java-mail/issues/447" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/447/hovercard">#447</a>: Enhancement: allow defaults/overrides to ignore individual fields (turn off for specific properties)</li>
<li>v8.0.0 (08-March-2023): <a href="https://github.com/bbottema/simple-java-mail/issues/446" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/446/hovercard">#446</a>: Enhancement: add missing defaults properties for DKIM</li>
</ul>
<p dir="auto"><strong>This release changes how Email instances are built, or more specifically, when defaults and overrides are applied.
There are now overloaded build methods that provide similar behaviour as previous versions.</strong></p>
<p dir="auto">v7.9.0 - <a href="https://repo1.maven.org/maven2/org/simplejavamail/simple-java-mail/7.9.1/" rel="nofollow">v7.9.1</a></p>
<ul dir="auto">
<li>v7.9.1 (22-February-2023): <a href="https://github.com/bbottema/simple-java-mail/issues/444" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/444/hovercard">#444</a> Bugfix: encoded delimited recipients in EML not parsed properly</li>
<li>v7.9.0 (21-February-2023): <a href="https://github.com/bbottema/simple-java-mail/issues/344" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/344/hovercard">#344</a> Enhancement: make DKIM signing more flexible by allowing header exclusions in DKIM signature</li>
</ul>
<p dir="auto">v7.8.0 - <a href="https://repo1.maven.org/maven2/org/simplejavamail/simple-java-mail/7.8.3/" rel="nofollow">v7.8.3</a></p>
<ul dir="auto">
<li>v7.8.3 (21-February-2023): <a href="https://github.com/bbottema/simple-java-mail/issues/293" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/293/hovercard">#293</a> Bugfix: Decoding missing in a few placed when parsing MimeMessage or sending an Email</li>
<li>v7.8.2 (09-February-2023): <a href="https://github.com/bbottema/simple-java-mail/issues/442" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/442/hovercard">#442</a> Enhancement: Simple Java Mail should throw an exception when trying to utilize S/MIME with smime-module on the classpath</li>
<li>v7.8.1 (01-February-2023): <a href="https://github.com/bbottema/simple-java-mail/issues/438" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/438/hovercard">#438</a> Bug: properly Fail-Fast in case of Transport claim timeout in the batch-module, rather than running into NPE further down the line</li>
<li>v7.8.0 (24-January-2023): <a href="https://github.com/bbottema/simple-java-mail/issues/436" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/436/hovercard">#436</a> Enhancement: add mailerBuilder.withTransportModeLoggingOnly() as mailer API entry point</li>
<li>v7.8.0 (24-January-2023): <a href="https://github.com/bbottema/simple-java-mail/issues/435" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/435/hovercard">#435</a> Enhancement: SMTP server config should be optional in case a CustomMailer is used</li>
<li>v7.8.0 (24-January-2023): <a href="https://github.com/bbottema/simple-java-mail/issues/427" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/427/hovercard">#427</a> Feature: set a maximum email size on Mailer level which throws EmailToBig exception when exceeded</li>
</ul>
<p dir="auto">v7.7.0 - <a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C7.7.1%7Cjar" rel="nofollow">v7.7.1</a></p>
<ul dir="auto">
<li>v7.7.1 (18-January-2023): <a href="https://github.com/bbottema/simple-java-mail/issues/434" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/434/hovercard">#434</a> Regression bug in #430: Email parameter missing in CustomMailer interface</li>
<li>v7.7.0 (17-January-2023): <a href="https://github.com/bbottema/simple-java-mail/issues/430" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/430/hovercard">#430</a> Enhancement: auto-reconnect (if needed) when reclaiming a Transport connection from the SMTP connection</li>
<li>v7.7.0 (17-January-2023): <a href="https://github.com/bbottema/simple-java-mail/issues/383" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/383/hovercard">#383</a> Feature: be able to set defaults and overrides on the Mailer level, rather than email or global level</li>
</ul>
<p dir="auto">7.7.0 moves the conversion of Email to MimeMessage to after a Transport instance has been selected (in case of a cluster of SMTP servers),
so we can apply defaults/overrides on the Mailer level, meaning you can configure 'global' values for individual SMTP servers
(like a fixed FROM per server).</p>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C7.6.0%7Cjar" rel="nofollow">v7.6.0</a> (05-January-2023)</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/421" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/421/hovercard">#421</a> Enhancement: Add support for OAUTH2 authentication</li>
</ul>
<p dir="auto">v7.5.0 - <a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C7.5.2%7Cjar" rel="nofollow">v7.5.2</a></p>
<ul dir="auto">
<li>v7.5.2 (25-December-2022): <a href="https://github.com/bbottema/simple-java-mail/issues/429" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/429/hovercard">#429</a> Bug: wrong username property used when password authentication is not needed</li>
<li>v7.5.1 (12-December-2022): <a href="https://github.com/bbottema/simple-java-mail/issues/416" data-hovercard-type="pull_request" data-hovercard-url="/bbottema/simple-java-mail/pull/416/hovercard">#416</a> Bug: Support encoder names regardless of their case ("base64" is the same as "BASE64")</li>
<li>v7.5.1 (12-December-2022): <a href="https://github.com/bbottema/simple-java-mail/issues/424" data-hovercard-type="pull_request" data-hovercard-url="/bbottema/simple-java-mail/pull/424/hovercard">#424</a> Maintenance: bump JMail dependency from 1.2.1 to 1.4.1</li>
<li>v7.5.0 (28-July-2022): <a href="https://github.com/bbottema/simple-java-mail/issues/411" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/411/hovercard">#411</a> Enhancement: expose validation sub steps in the MailerHelper class for the completeness check, CRLF inject scans and address validations</li>
<li>v7.5.0 (28-July-2022): <a href="https://github.com/bbottema/simple-java-mail/issues/410" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/410/hovercard">#410</a> Bug: CRLF injection scan missing for dispositionNotificationTo and returnReceiptTo</li>
<li>v7.5.0 (28-July-2022): <a href="https://github.com/bbottema/simple-java-mail/issues/390" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/390/hovercard">#390</a> Enhancement: make client sided validation optional, turning off address validation and CRLF injection detection</li>
</ul>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C7.5.1%7Cjar" rel="nofollow">v7.5.1</a> (12-December-2022)</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/416" data-hovercard-type="pull_request" data-hovercard-url="/bbottema/simple-java-mail/pull/416/hovercard">#416</a> Bug: Support encoder names regardless of their case ("base64" is the same as "BASE64")</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/424" data-hovercard-type="pull_request" data-hovercard-url="/bbottema/simple-java-mail/pull/424/hovercard">#424</a> Maintenance: bump JMail dependency from 1.2.1 to 1.4.1</li>
</ul>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C7.5.0%7Cjar" rel="nofollow">v7.5.0</a> (28-July-2022)</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/411" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/411/hovercard">#411</a> Enhancement: expose validation sub steps in the MailerHelper class for the completeness check, CRLF inject scans and address validations</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/410" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/410/hovercard">#410</a> Bug: CRLF injection scan missing for dispositionNotificationTo and returnReceiptTo</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/390" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/390/hovercard">#390</a> Enhancement: make client sided validation optional, turning off address validation and CRLF injection detection</li>
</ul>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C7.4.0%7Cjar" rel="nofollow">v7.4.0</a> (19-July-2022)</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/407" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/407/hovercard">#407</a> Enhancement: Process all Outlook message headers, either copying the as-is or translating them to respective Simple Java Mail API calls</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/404" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/404/hovercard">#404</a> Minor bugfix: the new attachment's contentDescription was missing in Email.toString()</li>
</ul>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C7.3.0%7Cjar" rel="nofollow">v7.3.0</a> (15-July-2022)</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/405" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/405/hovercard">#405</a> Feature: Expand email builder API to support forced content Content-Transfer-Encoding for attachments, like quoted-printable, base64, 7BIT and others</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/404" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/404/hovercard">#404</a> Feature: Expand email builder API to support Content-Description on attachments</li>
</ul>
<p dir="auto">v7.2.0 - <a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C7.2.1%7Cjar" rel="nofollow">v7.2.1</a></p>
<ul dir="auto">
<li>v7.2.1 (13-July-2022): <a href="https://github.com/bbottema/simple-java-mail/issues/396" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/396/hovercard">#396</a> Enhancement: make Outlook support tolerant of invalid/empty nested Outlook message attachments</li>
<li>v7.2.0 (13-July-2022): <a href="https://github.com/bbottema/simple-java-mail/issues/399" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/399/hovercard">#399</a> Feature: Expand email builder API to support <a href="https://www.simplejavamail.org/features.html#section-content-transfer-encoding" rel="nofollow">selective content encoding</a>, like quoted-printable, base64, 7BIT and others</li>
</ul>
<p dir="auto">v7.1.0 - <a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C7.1.3%7Cjar" rel="nofollow">v7.1.3</a></p>
<ul dir="auto">
<li>v7.1.3 (12-July-2022): <a href="https://github.com/bbottema/simple-java-mail/issues/403" data-hovercard-type="pull_request" data-hovercard-url="/bbottema/simple-java-mail/pull/403/hovercard">#403</a> Security: Bump zip4j (only used during testing)</li>
<li>v7.1.2 (12-July-2022): <a href="https://github.com/bbottema/simple-java-mail/issues/401" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/401/hovercard">#401</a> Enhancement: Add HEIC and WEBP support when dynamically resolving embedded images from classpath</li>
<li>v7.1.2 (12-July-2022): <a href="https://github.com/bbottema/simple-java-mail/issues/402" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/402/hovercard">#402</a> Security: Update Log4j to 2.17.1</li>
<li>v7.1.2 (12-July-2022): <a href="https://github.com/bbottema/simple-java-mail/issues/393" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/393/hovercard">#393</a> Security: Update Apache POI and POI Scratchpad</li>
<li>v7.1.1 (27-March-2022): <a href="https://github.com/bbottema/simple-java-mail/issues/387" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/387/hovercard">#387</a> Bug: memory leak in SMPT connection pool when 3rd party deallocation failed with exception</li>
<li>v7.1.0 (25-January-2022): <a href="https://github.com/bbottema/simple-java-mail/issues/379" data-hovercard-type="pull_request" data-hovercard-url="/bbottema/simple-java-mail/pull/379/hovercard">#379</a> Maintenance: Adjust dependencies and make Java 9+ friendly</li>
</ul>
<p dir="auto">v7.0.1 - <a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C7.0.2%7Cjar" rel="nofollow">v7.0.2</a></p>
<ul dir="auto">
<li>v7.0.2 (25-January-2022): <a href="https://github.com/bbottema/simple-java-mail/issues/329" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/329/hovercard">#329</a> Enhancement: Exceptions cause error-level logging in addition to rethrowing the exception, but should just include the message in a custom exception</li>
<li>v7.0.2 (25-January-2022): <a href="https://github.com/bbottema/simple-java-mail/issues/378" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/378/hovercard">#378</a> Bug: package org.simplejavamail.internal.modules causes split package problem in Java9+</li>
<li>v7.0.1 (22-January-2022): <a href="https://github.com/bbottema/simple-java-mail/issues/375" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/375/hovercard">#375</a> Bug: <a href="https://www.simplejavamail.org/features.html#section-sending-asynchronously" rel="nofollow">batch-module</a> gives error when there is a <a href="https://www.simplejavamail.org/features.html#section-custom-mailer" rel="nofollow">custom mailer</a></li>
</ul>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C7.0.0%7Cjar" rel="nofollow">v7.0.0</a> (2-January-2022)</p>
<p dir="auto">It has been two years since the last major release, but 7.0.0 finally here!</p>
<h4 dir="auto"><a id="user-content-whats-new" class="anchor" aria-hidden="true" href="#whats-new"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a>What's new</h4>
<p dir="auto">Major features:</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/322" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/322/hovercard">#322</a> Simple Java Mail migrated to Java 8 finally (see notes below)</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/295" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/295/hovercard">#295</a> And also switched to JavaMail's successor Jakarta Mail 2.0.1 (see notes below)</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/323" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/323/hovercard">#323</a> Solved the great CLI performance problem (now executes near instantly)</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/319" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/319/hovercard">#319</a> Replaced the underlying regex-based email-address validation library with the lexer based <a href="https://github.com/RohanNagar/jmail">JMail</a>, which is faster, <a href="https://www.rohannagar.com/jmail/" rel="nofollow">correcter</a>, documented better and is more up-to-date with RFC's</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/367" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/367/hovercard">#367</a> The sendMail/testConnection methods now have proper support for <code>CompletableFuture</code></li>
</ul>
<p dir="auto">Bugfixes:</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/352" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/352/hovercard">#352</a> Bug: names regex groups are not supported in Android JVM</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/326" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/326/hovercard">#326</a> Bug: NullPointer when parsing Outlook Message with nested empty Outlook message</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/330" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/330/hovercard">#330</a> Bug: cli expected --mailer arguments duplicated 3 times</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/324" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/324/hovercard">#324</a> Bug: Add back missing log4j2 for CLI library</li>
</ul>
<p dir="auto">Maintenance:</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/368" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/368/hovercard">#368</a> Resolve log4j (Java8) <a href="https://logging.apache.org/log4j/2.x/security.html" rel="nofollow">vulnerability</a> in Simple Java Mail's CLI module</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/330" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/330/hovercard">#330</a> Improved feedback from failing CLI commands</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/327" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/327/hovercard">#327</a> Implement toString() for Mailer instances for debugging purposes</li>
</ul>
<h4 dir="auto"><a id="user-content-about-the-migration" class="anchor" aria-hidden="true" href="#about-the-migration"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a>About the migration</h4>
<p dir="auto">Updating to Java8/Jakarta 2.0.1 posed a challenge as the 3rd party S/MIME library <a href="https://github.com/markenwerk/java-utils-mail-smime">java-utils-mail-smime</a> has been abandoned/archived while developing Simple Java Mail. Furthermore, it was still under LGPL3 license while everything else is ApacheV2.</p>
<p dir="auto">Thankfully, I obtained permissions from the maintainers -as well as original developers from decades ago on SourceForge- to take both java-utils-mail-smime and java-utils-mail-dkim under my wings at Simple Java Mail and change the licensing model! You can now post issues and pull requests here:</p>
<ul dir="auto">
<li><a href="https://github.com/simple-java-mail/java-utils-mail-smime">simple-java-mail/java-utils-mail-smime</a></li>
<li><a href="https://github.com/simple-java-mail/java-utils-mail-dkim">simple-java-mail/java-utils-mail-dkim</a></li>
</ul>
<p dir="auto">v6.7.0 - <a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C6.7.6%7Cjar" rel="nofollow">v6.7.6</a></p>
<ul dir="auto">
<li>v6.7.6 (22-January-2022): <a href="https://github.com/bbottema/simple-java-mail/issues/375" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/375/hovercard">#375</a> Bug: <a href="https://www.simplejavamail.org/features.html#section-sending-asynchronously" rel="nofollow">batch-module</a> gives error when there is a <a href="https://www.simplejavamail.org/features.html#section-custom-mailer" rel="nofollow">custom mailer</a></li>
<li>v6.7.5 (26-December-2021): <a href="https://github.com/bbottema/simple-java-mail/issues/338" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/338/hovercard">#338</a> Enhancement: Also return AsyncResponse from plain Mailer.sendEmail(singleArgument) as async can be configured through MailerBuilder now</li>
<li>v6.7.4 (25-December-2021): <a href="https://github.com/bbottema/simple-java-mail/issues/331" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/331/hovercard">#331</a> Enhancement: Coalesce empty SMTP server arguments to null to support CLI better</li>
<li>v6.7.3 (25-December-2021): <a href="https://github.com/bbottema/simple-java-mail/issues/335" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/335/hovercard">#335</a> Bugfix: Precondition nonNull check also checks nonEmpty and breaks on clearEmailAddressCriteria</li>
<li>v6.7.2 (25-December-2021): <a href="https://github.com/bbottema/simple-java-mail/issues/318" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/318/hovercard">#318</a> Maintenance: Allow zero data attachments so Outlook message conversions don't crash and burn</li>
<li>v6.7.1 (25-December-2021): <a href="https://github.com/bbottema/simple-java-mail/issues/346" data-hovercard-type="pull_request" data-hovercard-url="/bbottema/simple-java-mail/pull/346/hovercard">#346</a> Bugfix: Add option to parse MimeMessage without fetching attachment data from server - Properly return named datasource without fetching all the data if unwanted</li>
<li>v6.7.0 (25-December-2021): <a href="https://github.com/bbottema/simple-java-mail/issues/356" data-hovercard-type="pull_request" data-hovercard-url="/bbottema/simple-java-mail/pull/356/hovercard">#356</a> Enhancement: Improve for support for Android &lt; 8.0 (Fix NoClassDefFoundError)</li>
<li>v6.7.0 (25-December-2021): <a href="https://github.com/bbottema/simple-java-mail/issues/351" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/351/hovercard">#351</a> Bugfix: emlToEmail() and mimeMessageToEmail() break on mesages with duplicate names and legacy empty nested messages</li>
<li>v6.7.0 (25-December-2021): <a href="https://github.com/bbottema/simple-java-mail/issues/347" data-hovercard-type="pull_request" data-hovercard-url="/bbottema/simple-java-mail/pull/347/hovercard">#347</a> Maintenance: Reduce log-spam and prevent exception on every module availability check</li>
<li>v6.7.0 (25-December-2021): <a href="https://github.com/bbottema/simple-java-mail/issues/346" data-hovercard-type="pull_request" data-hovercard-url="/bbottema/simple-java-mail/pull/346/hovercard">#346</a> Feature: Add option to parse MimeMessage <a href="https://www.simplejavamail.org/features.html#section-converting" rel="nofollow">without fetching attachment data</a> from server</li>
</ul>
<p dir="auto">v6.6.0 - <a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C6.6.2%7Cjar" rel="nofollow">v6.6.2</a></p>
<ul dir="auto">
<li>v6.6.2 (23-December-2021): <a href="https://github.com/bbottema/simple-java-mail/issues/365" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/365/hovercard">#365</a> Security: Resolve log4j vulnerability in Simple Java Mail</li>
<li>v6.6.1 (12-June-2021): <a href="https://github.com/bbottema/simple-java-mail/issues/321" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/321/hovercard">#321</a> Enhancement: Ignore malformed recipient addresses and continue parsing email data</li>
<li>v6.6.0 (1-June-2021): <a href="https://github.com/bbottema/simple-java-mail/issues/320" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/320/hovercard">#320</a> Enhancement: Added <a href="https://www.simplejavamail.org/features.html#section-sending-smime" rel="nofollow">default S/MIME signing</a> to Mailer level and fixed crippling performance bug</li>
</ul>
<p dir="auto">v6.5.0 - <a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C6.5.4%7Cjar" rel="nofollow">v6.5.4</a></p>
<ul dir="auto">
<li>
<p dir="auto">v6.5.4 (22-May-2021): <a href="https://github.com/bbottema/simple-java-mail/issues/315" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/315/hovercard">#315</a> Enhancement: Nested attachments of Outlook message attachments are now preserved as standard EML MimeMessage attachments</p>
<p dir="auto"><strong>NOTE:</strong> This <em>removes</em> the Kryo dependency</p>
</li>
<li>
<p dir="auto">v6.5.3 (4-May-2021): <a href="https://github.com/bbottema/simple-java-mail/issues/314" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/314/hovercard">#314</a> Bugfix: Nested attachments of Outlook message attachments are now preserved, by utilizing Kryo</p>
<p dir="auto"><strong>NOTE:</strong> This add Kryo as extra dependency to the outlook-module (and is subsequently removed in 6.5.4)</p>
</li>
<li>
<p dir="auto">v6.5.2 (15-April-2021): <a href="https://github.com/bbottema/simple-java-mail/issues/311" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/311/hovercard">#311</a> Bugfix: text/calendar as string -&gt; ClassCastException (if calendar type is not Inputstream)</p>
</li>
<li>
<p dir="auto">v6.5.1 (10-April-2021): <a href="https://github.com/bbottema/simple-java-mail/issues/307" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/307/hovercard">#307</a> / <a href="https://github.com/bbottema/simple-java-mail/issues/310" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/310/hovercard">#310</a> Bugfix: embedded image resource name got mangled</p>
</li>
<li>
<p dir="auto">v6.5.0 (16-February-2021): <a href="https://github.com/bbottema/simple-java-mail/issues/298" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/298/hovercard">#298</a> Enhancement: Nested Outlook messages aren't discarded anymore, but parsed to serialized Email objects</p>
</li>
<li>
<p dir="auto">v6.5.0 (16-February-2021): <a href="https://github.com/bbottema/simple-java-mail/issues/292" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/292/hovercard">#292</a> Bugfix: NullPointerException in SmimeUtilFixed when protocol is missing (which is valid)</p>
</li>
<li>
<p dir="auto">v6.5.0 (16-February-2021): <a href="https://github.com/bbottema/simple-java-mail/issues/289" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/289/hovercard">#289</a> Bugfix: Support multiple headers with same key</p>
</li>
</ul>
<p dir="auto">This release breaks all GET/SET api regarding headers used as map (Map&lt;String, T&gt; -&gt; Map&lt;String, Collection&lt;T&gt;&gt;)
This release might break api in the rare case you relied on the attachment list and you have nested Outlook .msg attachments (previously omitted in the results)</p>
<p dir="auto">v6.4.0 - <a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C6.4.5%7Cjar" rel="nofollow">v6.4.5</a></p>
<ul dir="auto">
<li>v6.4.5 (13-Februari-2021): <a href="https://github.com/bbottema/simple-java-mail/issues/306" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/306/hovercard">#306</a> Maintenance: Update outlook-message-parser to 1.7.9</li>
<li>v6.4.5 (13-Februari-2021): <a href="https://github.com/bbottema/simple-java-mail/issues/304" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/304/hovercard">#304</a> Regression bugfix: batch-module needed for sending mails async, basic version should work without</li>
<li>v6.4.5 (13-Februari-2021): <a href="https://github.com/bbottema/simple-java-mail/issues/303" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/303/hovercard">#303</a> Bugfix: EML Attachments are modified/have the wrong size</li>
<li>v6.4.4 (25-October-2020): <a href="https://github.com/bbottema/simple-java-mail/issues/294" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/294/hovercard">#294</a> Always invoke async success/exception handlers even if set after sending email (behaving more like promises/futures)</li>
<li>v6.4.4 (25-October-2020): <a href="https://github.com/bbottema/simple-java-mail/issues/291" data-hovercard-type="pull_request" data-hovercard-url="/bbottema/simple-java-mail/pull/291/hovercard">#291</a> On Exception only log the email ID at error level and log the whole email at trace level</li>
<li>v6.4.4 (25-October-2020): <a href="https://github.com/bbottema/simple-java-mail/issues/290" data-hovercard-type="pull_request" data-hovercard-url="/bbottema/simple-java-mail/pull/290/hovercard">#290</a> Only perform expensive logging logic if respective logging level is enabled</li>
<li>v6.4.3 (6-August-2020): <a href="https://github.com/bbottema/simple-java-mail/issues/284" data-hovercard-type="pull_request" data-hovercard-url="/bbottema/simple-java-mail/pull/284/hovercard">#284</a> Improved support for Calendar attachments created by gMail</li>
<li>v6.4.3 (6-August-2020): <a href="https://github.com/bbottema/simple-java-mail/issues/283" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/283/hovercard">#283</a> Bugfix: Fix support for reading Calendar attachments with quoted-printable transfer-type</li>
<li>v6.4.2 (3-August-2020): <a href="https://github.com/bbottema/simple-java-mail/issues/281" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/281/hovercard">#281</a> Bugfix: Fix support for reading Calendar attachments</li>
<li>v6.4.1 (26-July-2020): <a href="https://github.com/bbottema/simple-java-mail/issues/252" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/252/hovercard">#252</a> Bugfix: Added missing support for S/MIME enveloped signing</li>
<li>v6.4.0 (19-July-2020): <a href="https://github.com/bbottema/simple-java-mail/issues/268" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/268/hovercard">#268</a> Immediately resolve InputStreams when building emails, don't reuse
<ul dir="auto">
<li>This primarily affects the builder api for S/MIME and DKIM signing / encryption.</li>
</ul>
</li>
</ul>
<p dir="auto">v6.3.0 - <a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C6.3.2%7Cjar" rel="nofollow">v6.3.2</a> (11-July-2020 - 12-July-2020)</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/271" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/271/hovercard">#271</a> Bugfix: Attachment (file)names with special characters should not be encoded</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/248" data-hovercard-type="pull_request" data-hovercard-url="/bbottema/simple-java-mail/pull/248/hovercard">#248</a> Bugfix: MimeMessageHelper: use complete filename as resource name</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/279" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/279/hovercard">#279</a> Allow <a href="https://www.simplejavamail.org/features.html#section-custom-properties" rel="nofollow">extra Session properties</a> configured through simplejavamail.properties</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/277" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/277/hovercard">#277</a> Add API for using <a href="http://localhost:3000/features.html#section-ssl-tls" rel="nofollow">custom SSLSocketFactory</a></li>
</ul>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C6.2.0%7Cjar" rel="nofollow">v6.2.0</a> (9-July-2020)</p>
<p dir="auto">This release adds the following major new feature:</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/260" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/260/hovercard">#260</a> <strong>Add support for <a href="https://www.simplejavamail.org/features.html#section-embedding" rel="nofollow">dynamic datasource resolution</a></strong> (file/url/classpath) for embedded images in HTML body</li>
</ul>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C6.1.0%7Cjar" rel="nofollow">v6.1.0</a> (5-July-2020)</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/264" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/264/hovercard">#264</a> Switch from AssertionError to IllegalStateException</li>
<li>Bumped outlook-message-parser from 1.7.3 to 1.7.5
<ul dir="auto">
<li>bugfix for parsing chinese unsent Outlook messages</li>
<li>bugfix Outlook attachments with special characters in the name</li>
</ul>
</li>
<li>Bumped email-rfc2822-validator from 2.1.3 to 2.2.0
<ul dir="auto">
<li>bugfix properly handle brackets in email addresses when allowed</li>
</ul>
</li>
<li>Bumped log4j-core from 2.6.1 to 2.13.2</li>
</ul>
<p dir="auto">v6.0.2 - <a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C6.0.5%7Cjar" rel="nofollow">v6.0.5</a> (21-January-2020 - 13-June-2020)</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/270" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/270/hovercard">#270</a> Bug: CLI module missing Jetbrains @Nullable annotation dependency needed in runtime</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/262" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/262/hovercard">#262</a> Bug: Executor settings passed to the builder are ignored</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/249" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/249/hovercard">#249</a> Bug: MimeMessageParser doesn't handle multiple attachments with the same name correctly</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/245" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/245/hovercard">#245</a> Bug: JDK9+ Incorrect JPMS Automatic-Module-Name</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/246" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/246/hovercard">#246</a> Bug: Sending async emails with and without the Batch module cause lingering threads</li>
</ul>
<p dir="auto">v6.0.0-rc1 - <a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C6.0.1%7Cjar" rel="nofollow">v6.0.1</a> (18-December-2019 - 24-January-2020)</p>
<p dir="auto">After almost two years of development the next major release 6.0.0 is finally here! And what a doozy it is, with the following major new features:</p>
<p dir="auto">The core library is now even smaller compared to the 5.x.x series going from 183kb to 134kb!</p>
<ul dir="auto">
<li><a href="https://www.simplejavamail.org/cli.html#navigation" rel="nofollow">CLI support!!</a>,</li>
<li>major performance improvement with <a href="https://www.simplejavamail.org/configuration.html#section-batch-and-clustering" rel="nofollow">advanced batch processing</a> including support for mail server clusters.</li>
<li>You can now replace the final sending of emails with <a href="https://www.simplejavamail.org/features.html#section-custom-mailer" rel="nofollow">your own logic</a>, using a 3rd party service of your choice.</li>
<li>6.0.0 also includes support for <a href="https://www.simplejavamail.org/features.html#section-smime" rel="nofollow">S/MIME signed and encrypted emails</a>!</li>
<li>All 3rd party dependencies have been made optional by splitting up Simple Java Mail into easy to use <a href="https://www.simplejavamail.org/modules.html#navigation" rel="nofollow">modules</a>.</li>
<li>You can now monitor and <a href="https://www.simplejavamail.org/features.html#section-handling-async-result" rel="nofollow">handle async processing</a> using Futures.</li>
<li>MimeMessage results are now <a href="https://www.simplejavamail.org/rfc-compliant.html#section-explore-multipart" rel="nofollow">structurally matched</a> to specific needs (only using alternative/mixed etc. when needed)</li>
</ul>
<p dir="auto">Here's the complete list of changes:</p>
<h4 dir="auto"><a id="user-content-new-features-and-enhancements" class="anchor" aria-hidden="true" href="#new-features-and-enhancements"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a>New features and enhancements</h4>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/183" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/183/hovercard">#183</a> To manage all the optional dependencies and related code, Simple Java Mail should be <a href="https://www.simplejavamail.org/modules.html#navigation" rel="nofollow">split up into modules</a></li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/156" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/156/hovercard">#156</a> Add <a href="https://www.simplejavamail.org/cli.html#navigation" rel="nofollow">CLI support</a></li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/214" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/214/hovercard">#214</a> Support more <a href="https://www.simplejavamail.org/features.html#section-sending-asynchronously" rel="nofollow">advanced batch processing</a> use cases</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/187" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/187/hovercard">#187</a> Simple Java Mail should have optional support for signed <a href="https://www.simplejavamail.org/modules.html#smime-module" rel="nofollow">S/MIME attachments</a></li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/121" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/121/hovercard">#121</a> Introduce interfaces for validation and sending, so these steps can be customized</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/144" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/144/hovercard">#144</a> Simple Java Mail should <a href="https://www.simplejavamail.org/migration-notes-6.0.0.html#mimemessage-structure" rel="nofollow">tailor the MimeMessage structure</a> to specific needs</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/138" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/138/hovercard">#138</a> Add support for <a href="https://www.simplejavamail.org/features.html#section-icalendar-vevent" rel="nofollow">Calendar events</a> (iCalendar vEvent)</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/235" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/235/hovercard">#235</a> Be able to <a href="https://www.simplejavamail.org/features.html#section-custom-sentdate" rel="nofollow">fix the sent date</a> for a new email</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/232" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/232/hovercard">#232</a> Improve encoding of attachment file names</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/222" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/222/hovercard">#222</a> Add config property support for trusting hosts and verifying server identity</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/212" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/212/hovercard">#212</a> Authenticated proxy server started even if already running, raising exception</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/207" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/207/hovercard">#207</a> Implement more comprehensive ThreadPoolExecutor and expose config options</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/211" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/211/hovercard">#211</a> SpringSupport should expose the intermediate builder for customization</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/193" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/193/hovercard">#193</a> Simple Java Mail should use default server ports when not provided by the user</li>
</ul>
<h4 dir="auto"><a id="user-content-bugs-solved" class="anchor" aria-hidden="true" href="#bugs-solved"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a>Bugs solved</h4>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/242" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/242/hovercard">#242</a> Renamed log4j2.xml to log4j2_example.xml so it doesn't clash with project config</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/241" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/241/hovercard">#241</a> EmailConverter.outlookMsgToEmail duplicates recipients</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/239" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/239/hovercard">#239</a> List of Recipients not ordered as added (insertion order not maintained)</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/236" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/236/hovercard">#236</a> Message ID should be mapped from Outlook messages as well</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/210" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/210/hovercard">#210</a> Connection/session timeout properties not set when not sending in batch mode</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/201" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/201/hovercard">#201</a> When parsing Outlook message, FROM address should default to a dummy address when missing</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/200" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/200/hovercard">#200</a> When parsing Outlook message, attachment name doesn't fallback on filename if proper name is empty</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/161" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/161/hovercard">#161</a> When reading (chinese) .msg files, HTML converted from RTF is completely garbled (encoding issue)</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/159" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/159/hovercard">#159</a> Can not parse email with blank email address headers</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/139" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/139/hovercard">#139</a> Multiple Bodyparts of same Content-Type not supported for text/html &amp; text/plain within Multipart/mixed or Multipart/alternative</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/151" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/151/hovercard">#151</a> Attachment's file extension overwritten by resource's invalid extension</li>
</ul>
<h4 dir="auto"><a id="user-content-maintenance-updates" class="anchor" aria-hidden="true" href="#maintenance-updates"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a>Maintenance updates</h4>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/165" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/165/hovercard">#165</a> Move away from Findbugs (unofficial JSR-305) annotations</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/164" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/164/hovercard">#164</a> The DKIM dependency has been updated to benefit from the newer Apache V2 license</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/164" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/164/hovercard">#164</a> The DKIM dependency has been updated to benefit from the newer Apache V2 license</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/184" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/184/hovercard">#184</a> Update JavaMail dependency to 1.6.2, adding support for UTF-8 charset</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/186" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/186/hovercard">#186</a> Update JavaMail dependency to 1.6.2, adding support for authenticated HTTP web proxy</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/146" data-hovercard-type="pull_request" data-hovercard-url="/bbottema/simple-java-mail/pull/146/hovercard">#146</a> Added OSGI manifest and switched to spotbugs</li>
</ul>
<h4 dir="auto"><a id="user-content-included-changes-from-outlook-message-parser" class="anchor" aria-hidden="true" href="#included-changes-from-outlook-message-parser"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a>Included changes from outlook-message-parser</h4>
<ul dir="auto">
<li>v6.0.1, v1.7.3: <a href="https://github.com/bbottema/outlook-message-parser/issues/27" data-hovercard-type="issue" data-hovercard-url="/bbottema/outlook-message-parser/issues/27/hovercard">#27</a> When from name/address are not available (unsent emails), these fields are filled with binary garbage</li>
<li>v6.0.1, v1.7.2: <a href="https://github.com/bbottema/outlook-message-parser/issues/26" data-hovercard-type="issue" data-hovercard-url="/bbottema/outlook-message-parser/issues/26/hovercard">#26</a> To email address is not handled properly when name is omitted</li>
<li>v6.0.0, v1.7.1: <a href="https://github.com/bbottema/outlook-message-parser/issues/25" data-hovercard-type="issue" data-hovercard-url="/bbottema/outlook-message-parser/issues/25/hovercard">#25</a> NPE on ClientSubmitTime when original message has not been sent yet</li>
<li>v6.0.0, v1.7.1: <a href="https://github.com/bbottema/outlook-message-parser/issues/23" data-hovercard-type="issue" data-hovercard-url="/bbottema/outlook-message-parser/issues/23/hovercard">#23</a> Bug: _<em>nameid</em> directory should not be parsed (and causing invalid HTML body)</li>
<li>v6.0.0, v1.7.0: <a href="https://github.com/bbottema/outlook-message-parser/issues/18" data-hovercard-type="issue" data-hovercard-url="/bbottema/outlook-message-parser/issues/18/hovercard">#18</a> Upgrade Apache POI 3.9 -&gt; 4.x (but managed back for Simple Java Mail due to incompatibility with Java 7)</li>
<li>v6.0.0, v1.6.0: <a href="https://github.com/bbottema/outlook-message-parser/issues/21" data-hovercard-type="issue" data-hovercard-url="/bbottema/outlook-message-parser/issues/21/hovercard">#21</a> Multiple TO recipients are not handles properly</li>
<li>v6.0.0, v1.5.0: <a href="https://github.com/bbottema/outlook-message-parser/issues/20" data-hovercard-type="issue" data-hovercard-url="/bbottema/outlook-message-parser/issues/20/hovercard">#20</a> CC and BCC recipients are not parsed properly</li>
<li>v6.0.0, v1.5.0: <a href="https://github.com/bbottema/outlook-message-parser/issues/19" data-hovercard-type="pull_request" data-hovercard-url="/bbottema/outlook-message-parser/pull/19/hovercard">#19</a> Use real Outlook ContentId Attribute to resolve CID Attachments</li>
<li>v6.0.0, v1.4.1: <a href="https://github.com/bbottema/outlook-message-parser/issues/17" data-hovercard-type="issue" data-hovercard-url="/bbottema/outlook-message-parser/issues/17/hovercard">#17</a> Fixed encoding error for UTF-8's Windows legacy name (cp)65001</li>
<li>v6.0.0, v1.4.0: <a href="https://github.com/bbottema/outlook-message-parser/issues/9" data-hovercard-type="issue" data-hovercard-url="/bbottema/outlook-message-parser/issues/9/hovercard">#9</a> Replaced the RFC to HTML converter with a brand new RFC-compliant convert! (thanks to @fadeyev!)</li>
<li>v6.0.0, v1.3.0: <a href="https://github.com/bbottema/outlook-message-parser/issues/14" data-hovercard-type="issue" data-hovercard-url="/bbottema/outlook-message-parser/issues/14/hovercard">#14</a> Dependency problem with Java9+, missing Jakarta Activation Framework</li>
<li>v6.0.0, v1.3.0: <a href="https://github.com/bbottema/outlook-message-parser/issues/13" data-hovercard-type="issue" data-hovercard-url="/bbottema/outlook-message-parser/issues/13/hovercard">#13</a> HTML start tags with extra space not handled correctly</li>
<li>v6.0.0, v1.3.0: <a href="https://github.com/bbottema/outlook-message-parser/issues/11" data-hovercard-type="issue" data-hovercard-url="/bbottema/outlook-message-parser/issues/11/hovercard">#11</a> SimpleRTF2HTMLConverter inserts too many <br> tags</li>
<li>v6.0.0, v1.3.0: <a href="https://github.com/bbottema/outlook-message-parser/issues/10" data-hovercard-type="issue" data-hovercard-url="/bbottema/outlook-message-parser/issues/10/hovercard">#10</a> Embedded images with DOS-like names are classified as attachments</li>
<li>v6.0.0, v1.3.0: <a href="https://github.com/bbottema/outlook-message-parser/issues/9" data-hovercard-type="issue" data-hovercard-url="/bbottema/outlook-message-parser/issues/9/hovercard">#9</a> SimpleRTF2HTMLConverter removes some valid tags during conversion</li>
<li>v6.0.0, v1.2.1: Ignore non S/MIME related content types when extracting S/MIME metadata</li>
<li>v6.0.0, v1.2.1: Added toString and equals methods to the S/MIME data classes</li>
<li>v6.0.0, v1.1.21: Upgraded mediatype recognition based on file extension for incomplete attachments</li>
<li>v6.0.0, v1.1.21: Added / improved support for public S/MIME meta data</li>
<li>v6.0.0, v1.1.20: <a href="https://github.com/bbottema/outlook-message-parser/issues/7" data-hovercard-type="issue" data-hovercard-url="/bbottema/outlook-message-parser/issues/7/hovercard">#7</a> Fix missing S/MIME header details that are needed to determine the type of S/MIME application</li>
<li>v6.0.0, v1.1.19: Log rtf compression error, but otherwise ignore it and keep going and extract what we can.</li>
</ul>
<p dir="auto"><strong>A big shout out to @dnault (<a href="https://github.com/dnault/therapi-runtime-javadoc">runtime javadoc</a>), @remkop (<a href="https://picocli.info/" rel="nofollow">picocli</a>) and @markenwerk
(<a href="https://github.com/markenwerk/java-utils-mail-smime">S/MIME</a> and <a href="https://github.com/markenwerk/java-utils-mail-dkim">DKIM</a>) for working with me to make the
libraries work with JDK7+ and do what Simple Java Mail needed! Finally a great many thanks the numerous contributors on Simple Java Mail as well as
<a href="https://github.com/bbottema/outlook-message-parser">outlook-message-parser</a> - this release would not be there without you.</strong></p>
<p dir="auto">v5.5.0 - <a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C5.5.1%7Cjar" rel="nofollow">v5.5.1</a></p>
<ul dir="auto">
<li>v5.5.1 (20-October-2019): <a href="https://github.com/bbottema/simple-java-mail/issues/230" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/230/hovercard">#230</a> Bugfix: Missing address value in address headers (ie. Return-Path) not handled properly, resulting in Exception</li>
<li>v5.5.0 (15-October-2019): <a href="https://github.com/bbottema/simple-java-mail/issues/229" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/229/hovercard">#229</a> Bugfix: Timeouts not working for synchronous sendMail calls.</li>
</ul>
<p dir="auto">If you had connection properties configured for non-async send jobs, only now they will actually start to take effect.</p>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C5.4.0%7Cjar" rel="nofollow">v5.4.0</a> (28-August-2019)</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/221" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/221/hovercard">#221</a> API bugfix: server identity verification should not be tied to host trusting</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/226" data-hovercard-type="pull_request" data-hovercard-url="/bbottema/simple-java-mail/pull/226/hovercard">#226</a> Bug fix: Attachments with spaces in name are not handled properly</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/218" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/218/hovercard">#218</a> Enhancement: make Email serializable</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/227" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/227/hovercard">#227</a> Enhancement: Make parsing recipients from EML file more lenient</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/225" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/225/hovercard">#225</a> Enhancement: Clarify dependency on Jakarta Activation: DataSources no longer work on Java 9+</li>
</ul>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C5.3.0%7Cjar" rel="nofollow">v5.3.0</a> (16-August-2019)</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/215" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/215/hovercard">#215</a> Bug: Current DKIM header canonicalization can lead to invalid DKIM</li>
</ul>
<p dir="auto">Note this release should have no impact, but nonetheless is a minor update so you can determine for yourself if this update would cause issues.
The release changes DKIM header canonicalization from SIMPLE to RELAXED.</p>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C5.2.1%7Cjar" rel="nofollow">v5.2.1</a> (16-August-2019)</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/219" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/219/hovercard">#219</a> Bug: MimeMessageParser rejects attachments with duplicate names</li>
</ul>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C5.2.0%7Cjar" rel="nofollow">v5.2.0</a> (7-July-2019)</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/213" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/213/hovercard">#213</a> Update from javax.mail:1.6.0 to jakarta.mail:1.6.3</li>
</ul>
<p dir="auto">Note that dependencies that switched as well have been updated as part of this change. This includes the optional DKIM library and the email validation library:</p>
<ul dir="auto">
<li>net.markenwerk:utils-mail-dkim (1.1.10 -&gt; 1.2.0)</li>
<li>com.github.bbottema:emailaddress-rfc2822 (1.1.2 -&gt; 2.1.3)</li>
</ul>
<p dir="auto">v5.1.1 - <a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C5.1.7%7Cjar" rel="nofollow">v5.1.7</a></p>
<ul dir="auto">
<li>v5.1.7 (22-May-2019): <a href="https://github.com/bbottema/simple-java-mail/issues/171" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/171/hovercard">#171</a> Header validation tripping on known safe emails due to References header</li>
<li>v5.1.6 (27-April-2019): <a href="https://github.com/bbottema/simple-java-mail/issues/204" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/204/hovercard">#204</a> A Concurrent exception when an async process starts when the previous connection pool didn't shutdown in time</li>
<li>v5.1.6 (27-April-2019): <a href="https://github.com/bbottema/simple-java-mail/issues/204" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/204/hovercard">#204</a> B Exceptions in threads are now caught and logged and don't bubble up anymore. Note that more comprehensive exception handling will be available in 6.0.0 (<a href="https://github.com/bbottema/simple-java-mail/issues/148" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/148/hovercard">#148</a>).</li>
<li>v5.1.5 (24-April-2019): <a href="https://github.com/bbottema/simple-java-mail/issues/202" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/202/hovercard">#202</a> Fixed ConcurrentModificationException when moving invalid embedded images as regular attachments</li>
<li>v5.1.4 (5-April-2019): <a href="https://github.com/bbottema/simple-java-mail/issues/163" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/163/hovercard">#163</a> Fixed missing mimetype for attachments when parsing Outlook messages where mimeTag was not included</li>
<li>v5.1.3 (15-Januari-2019): Updated to newer rfc-validator version, which fixed a regression bug in that library</li>
<li>v5.1.2 (9-Januari-2019): <a href="https://github.com/bbottema/simple-java-mail/issues/189" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/189/hovercard">#189</a> Bugfix for missing timeout config for .testConnection() function</li>
<li>v5.1.1 (22-December-2018): <a href="https://github.com/bbottema/simple-java-mail/issues/190" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/190/hovercard">#190</a> Fix for transitive dependency clash because of emailaddress-rfc2822 library</li>
</ul>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C5.1.0%7Cjar" rel="nofollow">v5.1.0</a> (21-November-2018)</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/179" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/179/hovercard">#179</a> You can now <a href="https://www.simplejavamail.org/features.html#section-connection-test" rel="nofollow">test the connection</a> to the SMTP server</li>
</ul>
<p dir="auto">v5.0.1 - <a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C5.0.8%7Cjar" rel="nofollow">v5.0.8</a></p>
<ul dir="auto">
<li>v5.0.8 (27-Oktober-2018): <a href="https://github.com/bbottema/simple-java-mail/issues/178" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/178/hovercard">#178</a> Fix the annoying vulnerability Github report about spring-core</li>
<li>v5.0.7 (27-Oktober-2018): <a href="https://github.com/bbottema/simple-java-mail/issues/175" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/175/hovercard">#175</a> Attachment names are not always parsed properly from MimeMessage</li>
<li>v5.0.6 (3-Oktober-2018): <a href="https://github.com/bbottema/simple-java-mail/issues/167" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/167/hovercard">#167</a> Email addresses validated despite cleared validation validation criteria</li>
<li>v5.0.5 (3-Oktober-2018): <a href="https://github.com/bbottema/simple-java-mail/issues/137" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/137/hovercard">#137</a> When replying to an email with HTML, the result body is empty</li>
<li>v5.0.4 (22-September-2018): <a href="https://github.com/bbottema/simple-java-mail/issues/168" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/168/hovercard">#168</a> Properties aquired through ConfigLoader should be typed explicitly and converted if necessary</li>
<li>v5.0.3 (11-April-2018): <a href="https://github.com/bbottema/simple-java-mail/issues/136" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/136/hovercard">#136</a> ServerConfig class should be public API</li>
<li>v5.0.2 (7-April-2018): <a href="https://github.com/bbottema/simple-java-mail/issues/135" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/135/hovercard">#135</a> trustingAllHosts should be public on the Builder API</li>
<li>v5.0.2 (7-April-2018): <a href="https://github.com/bbottema/simple-java-mail/issues/131" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/131/hovercard">#131</a> NamedDataSource should implement EncodingAware</li>
<li>v5.0.1 (10-March-2018): <a href="https://github.com/bbottema/simple-java-mail/issues/130" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/130/hovercard">#130</a> java.lang.ClassNotFoundException: net.markenwerk.utils.mail.dkim.DkimMessage. Solves the issue of missing optional class DKIM even when not used</li>
</ul>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C5.0.0%7Cjar" rel="nofollow">v5.0.0</a> (14-Februari-2018)</p>
<p dir="auto">Also see the <a href="https://www.simplejavamail.org/migration-notes-5.0.0.html#navigation" rel="nofollow">migration notes</a></p>
<h4 dir="auto"><a id="user-content-new-features" class="anchor" aria-hidden="true" href="#new-features"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a>New features</h4>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/116" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/116/hovercard">#116</a> You can now test the connection to the SMTP server</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/115" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/115/hovercard">#115</a> Create mailers with a very robust MailerBuilder API, able to ignore defaults as well</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/114" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/114/hovercard">#114</a> Create emails with a very robust EmailBuilder API, able to ignore defaults as well. Now includes support for InternetAddress. Also copy emails.</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/107" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/107/hovercard">#107</a> You can now easily forward or reply to emails!</li>
</ul>
<h4 dir="auto"><a id="user-content-security-updates" class="anchor" aria-hidden="true" href="#security-updates"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a>Security updates</h4>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/111" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/111/hovercard">#111</a> Protocol properties for SMTPS are now applied properly</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/105" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/105/hovercard">#105</a> SMTP tries to upgrade to TLS while SMTP_TLS now enforces it and for both SMTP_TLS and SMTPS, <a href="https://javaee.github.io/javamail/docs/api/com/sun/mail/smtp/package-summary.html" rel="nofollow">mail.smtp.ssl.checkserveridentity</a> is set to true</li>
</ul>
<h4 dir="auto"><a id="user-content-maintenance-updates-1" class="anchor" aria-hidden="true" href="#maintenance-updates-1"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a>Maintenance updates</h4>
<p dir="auto">Complete <a href="https://www.javadoc.io/doc/org.simplejavamail/simple-java-mail" rel="nofollow">Javadoc</a> overhaul. Navigating the Javadoc should be much more consistent now (builder API being the single <em>public</em> source of truth).</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/122" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/122/hovercard">#122</a> The email-rfc2822-validator library has been made a proper Maven dependency (not packaged along anymore)</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/120" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/120/hovercard">#120</a> The DKIM library has been made an optional proper Maven dependency (not packaged along anymore)</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/119" data-hovercard-type="pull_request" data-hovercard-url="/bbottema/simple-java-mail/pull/119/hovercard">#119</a> Switched optional Spring dependency version to property and now testing with 4.3.11.RELEASE</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/113" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/113/hovercard">#113</a> Updated the underlying JavaMail to 1.6.0</li>
</ul>
<h4 dir="auto"><a id="user-content-bugfixes" class="anchor" aria-hidden="true" href="#bugfixes"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a>Bugfixes</h4>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/110" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/110/hovercard">#110</a> Trusted hosts should be space-delimited</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/109" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/109/hovercard">#109</a> Email headers should be allowed to be empty (now conversion errors can occur as well)</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/103" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/103/hovercard">#103</a> Converting to MimeMessage results in an invalid Content-Disposition for attachments</li>
</ul>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C4.4.5%7Cjar" rel="nofollow">v4.4.5</a> (2-September-2017)</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/101" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/101/hovercard">#101</a> API backwards compatibility update, reinstate old addRecipient API as deprecated (sorry for removing it abruptly)</li>
</ul>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C4.4.4%7Cjar" rel="nofollow">v4.4.4</a> (23-August-2017)</p>
<p dir="auto">API usability release. <strong>This relase streamlined the recipient setters, breaking backwards compatibility (but straightforward to fix)</strong></p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/95" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/95/hovercard">#95</a> Feature: Add support native API for <a href="https://www.simplejavamail.org/features.html#section-return-receipt" rel="nofollow">setting Return-Receipt-To</a> header</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/93" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/93/hovercard">#93</a> Feature: Add support native API for setting <a href="https://www.simplejavamail.org/features.html#section-return-receipt" rel="nofollow">Disposition-Notification-To</a> header</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/91" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/91/hovercard">#91</a> <strong>Feature: Add support for parsing <a href="https://www.simplejavamail.org/features.html#section-add-recipients" rel="nofollow">preformatted email addresses</a> that include both name and address</strong></li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/94" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/94/hovercard">#94</a> Bugfix: A single EmailBuilder would build emails that all share the same collections for recipients, attachments and embedded images</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/98" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/98/hovercard">#98</a> Bugfix: Subject and body content should be optional</li>
</ul>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C4.3.0%7Cjar" rel="nofollow">v4.3.0</a> (12-August-2017)</p>
<p dir="auto">Security and timeout release.</p>
<p dir="auto">This version safeguards against SMTP injection attack from external values entering the library through <em>Email</em> instance. Also, this release introduces default/configurable timeouts for connecting, reading and writing when sending an email.</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/89" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/89/hovercard">#89</a> Support multiple delimited recipient addresses sharing the same TO/CC/BCC name</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/88" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/88/hovercard">#88</a> <strong>Safeguard subject property (and others) against SMTP CRLF injection attacks</strong></li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/85" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/85/hovercard">#85</a> <strong>Apply configurable timeouts when sending emails</strong></li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/83" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/83/hovercard">#83</a> Parse INLINE attachments without ID as regular attachments when converting (mostly applicable to Apple emails)</li>
</ul>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C4.2.3%7Cjar" rel="nofollow">v4.2.3</a> (21-May-2017)</p>
<ul dir="auto">
<li>
<p dir="auto"><a href="https://github.com/bbottema/simple-java-mail/issues/79" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/79/hovercard">#79</a>: Enhancement: define custom message ID on the Email object</p>
</li>
<li>
<p dir="auto"><a href="https://github.com/bbottema/simple-java-mail/issues/74" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/74/hovercard">#74</a>: v4.2.3-java-6-release: A java6 version with limited capabilities:
I've released a customised java6 release with a customised outlook-message-parser 1.1.16-java6-release. <strong>This is the last java6 release</strong> I will do, as it is simply too much manual labor to create a limited second edition.</p>
<p dir="auto">For this edition, I've removed the JDK7 Phaser completely which has the following consequences:</p>
<ul dir="auto">
<li>If authenticated proxy is used, the bridging proxy server will not be shut down automatically (and might not run the second time)</li>
<li>If mails are sent in async mode, the connection pool will not be shut down anymore by itself</li>
</ul>
<p dir="auto">This means your server/application might not stop properly due to lingering processes. To be completely safe, only send emails in sync mode (used by default) and don't use authenticated proxy config.</p>
</li>
</ul>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C4.2.2%7Cjar" rel="nofollow">v4.2.2</a> (10-May-2017)</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/73" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/73/hovercard">#73</a>: Patch: fix for sending emails in async mode, which makes sure the connection pool is always closed when the last <em>known</em> email has been sent. Without this fix, the connection pool keeps any parent process running (main thread or Tomcat for example) until a hard kill.</li>
</ul>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C4.2.1%7Cjar" rel="nofollow">v4.2.1</a> (12-Feb-2017)</p>
<p dir="auto">Patch: streamlined convenience methods for adding recipients.</p>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C4.2.0%7Cjar" rel="nofollow">v4.2.0</a> (12-Feb-2017)</p>
<p dir="auto"><strong>Major feature: Using the EmailConverter you can now <a href="https://www.simplejavamail.org/features.html#section-converting" rel="nofollow">convert between</a> Outlook .msg, EML, MimeMessage and Email</strong>!</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/66" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/66/hovercard">#66</a>: Feature: <a href="https://www.simplejavamail.org/features.html#section-converting" rel="nofollow">convert</a> email to EML</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/65" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/65/hovercard">#65</a>: Feature: <a href="https://www.simplejavamail.org/modules.html#outlook-module" rel="nofollow">read outlook messages</a> from .msg file</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/64" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/64/hovercard">#64</a>: <strong>Feature: Added support for <a href="https://www.simplejavamail.org/debugging.html#section-debug-mode" rel="nofollow">logging-only mode</a> that skips the actual sending of emails</strong></li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/63" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/63/hovercard">#63</a>: Feature: Already including in previous patch update: <a href="https://www.simplejavamail.org/modules.html#spring-module" rel="nofollow">Spring support</a> (read properties from Spring context)</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/69" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/69/hovercard">#69</a>: Enhancement: Expanded EmailBuilder API to inlude more options for setting (multiple) recipients</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/70" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/70/hovercard">#70</a>: Enhancement: Most public API now have defensive null-checks for required fields (Fail Fast support)</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/68" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/68/hovercard">#68</a>: Bugfix: Name should be required for embedded images (added safeguards)</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/67" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/67/hovercard">#67</a>: Bugfix: Error when name was omitted for attachment</li>
<li>minor: added methods on AttachmentResource that reads back the content as (encoded) String</li>
<li>other: internal testing is now done using Wiser SMTP test server for testing live sending emails</li>
</ul>
<p dir="auto"><strong>Note</strong>: Starting this release, there will always be a Java6 compatible release as well versioned: "x.y.z-java6-release"</p>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C4.1.3%7Cjar" rel="nofollow">v4.1.3</a> (28-Jan-2017)</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/61" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/61/hovercard">#61</a>: Feature: Add support for <a href="https://www.simplejavamail.org/features.html#section-custom-properties" rel="nofollow">providing your own Properties</a> object</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/63" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/63/hovercard">#63</a>: <strong>Feature: <a href="https://www.simplejavamail.org/modules.html#spring-module" rel="nofollow">Spring support</a> (read properties from Spring context)</strong></li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/58" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/58/hovercard">#58</a>: Bugfix: Add support for non-English attachment and embedded image names</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/62" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/62/hovercard">#62</a>: Bugfix: Empty properties loaded from config should be considered null</li>
</ul>
<p dir="auto"><strong>NOTE</strong>: ConfigLoader moved from <code>/internal/util</code> to <code>/util</code></p>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C4.1.2%7Cjar" rel="nofollow">v4.1.2</a> (07-Nov-2016)</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/52" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/52/hovercard">#52</a>: bug fix for windows / linux disparity when checking socket status</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/56" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/56/hovercard">#56</a>: bug fix for IOException when signing dkim with a File reference</li>
</ul>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C4.1.1%7Cjar" rel="nofollow">v4.1.1</a> (30-Jul-2016)</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/50" data-hovercard-type="pull_request" data-hovercard-url="/bbottema/simple-java-mail/pull/50/hovercard">#50</a>: bug fix for manual naming datasources</li>
</ul>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C4.1.0%7Cjar" rel="nofollow">v4.1.0</a> (22-Jul-2016)</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/48" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/48/hovercard">#48</a>: Added programmatic support trusting hosts for SSL connections</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/47" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/47/hovercard">#47</a>: Honor given names, deduce extension from datasource name, and more robust support for parsing mimemessages</li>
</ul>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.simplejavamail%7Csimple-java-mail%7C4.0.0%7Cjar" rel="nofollow">v4.0.0</a> (05-Jul-2016)</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/41" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/41/hovercard">#41</a>: added support for fast parallel batch processing</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/42" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/42/hovercard">#42</a>: <strong>added support for config files</strong></li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/43" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/43/hovercard">#43</a>: removed logging implementation dependencies from distribution and documented various sample configs</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/39" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/39/hovercard">#39</a>: simplified and renamed packages to reflect the domain name of the new website: <a href="https://www.simplejavamail.org" rel="nofollow">simplejavamail.org</a></li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/38" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/38/hovercard">#38</a>: added support for anonymous proxy</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/38" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/38/hovercard">#38</a>: <strong>added support for authenticated proxy</strong></li>
</ul>
<p dir="auto"><strong>NOTE</strong>: All packages have been renamed to "org.simplejavamail.(..)"
<strong>NOTE</strong>: Switched to Java 7</p>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.codemonkey.simplejavamail%7Csimple-java-mail%7C3.1.1%7Cjar" rel="nofollow">v3.1.1</a> (11-May-2016)</p>
<p dir="auto"><strong>Major feature: DKIM support</strong>!</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/36" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/36/hovercard">#36</a>: Added proper toString and equals methods for the Email classes</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/33" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/33/hovercard">#33</a>: Added <a href="https://www.simplejavamail.org/features.html#section-dkim" rel="nofollow">support for DKIM</a> domain key signing</li>
</ul>
<p dir="auto"><em>NOTE</em>: this is the last release still using Java 6. Next release will be using Java 7.
/edit: starting with 4.2.0 every release will now have a "x.y.z-java6-release" release as well</p>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.codemonkey.simplejavamail%7Csimple-java-mail%7C3.0.2%7Cjar" rel="nofollow">v3.0.2</a> (07-May-2016)</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/35" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/35/hovercard">#35</a>: added proper .equals() and .toString() methods</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/34" data-hovercard-type="pull_request" data-hovercard-url="/bbottema/simple-java-mail/pull/34/hovercard">#34</a>: Fixed bug when disposition is missing (assume it is an attachment)</li>
<li>other: added findbugs support internally</li>
</ul>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.codemonkey.simplejavamail%7Csimple-java-mail%7C3.0.1%7Cjar" rel="nofollow">v3.0.1</a> (29-Feb-2016)</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/31" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/31/hovercard">#31</a>: Fixed EmailAddressCriteria.DEFAULT and clarified Javadoc</li>
</ul>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.codemonkey.simplejavamail%7Csimple-java-mail%7C3.0.0%7Cjar" rel="nofollow">v3.0.0</a> (26-Feb-2016)</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/30" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/30/hovercard">#30</a>: Improved the demonstration class to include attachments and embedded images</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/29" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/29/hovercard">#29</a>: The package has been restructured for future maintenance, breaking backwards compatibility</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/28" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/28/hovercard">#28</a>: Re-added improved email validation facility</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/22" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/22/hovercard">#22</a>: Added conversion to and from MimeMessage. You can now consume and produce MimeMessage objects with simple-java-mail</li>
</ul>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.codemonkey.simplejavamail%7Csimple-java-mail%7C2.5.1%7Cjar" rel="nofollow">v2.5.1</a> (19-Jan-2016)</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/25" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/25/hovercard">#25</a>: Added finally clause that will always close socket properly in case of an exception</li>
</ul>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.codemonkey.simplejavamail%7Csimple-java-mail%7C2.5%7Cjar" rel="nofollow">v2.5</a> (19-Jan-2016)</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/24" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/24/hovercard">#24</a>: Updated dependencies SLF4J to 1.7.13 and switched to the updated javax mail package com.sun.mail:javax.mail 1.5.5</li>
</ul>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.codemonkey.simplejavamail%7Csimple-java-mail%7C2.4%7Cjar" rel="nofollow">v2.4</a> (12-Aug-2015)</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/21" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/21/hovercard">#21</a>: builder API uses CC and BCC recipient types incorrectly</li>
</ul>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.codemonkey.simplejavamail%7Csimple-java-mail%7C2.3%7Cjar" rel="nofollow">v2.3</a> (21-Jul-2015)</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/19" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/19/hovercard">#19</a>: supporting custom Session Properties now and emergency access to internal Session object.</li>
</ul>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.codemonkey.simplejavamail%7Csimple-java-mail%7C2.2%7Cjar" rel="nofollow">v2.2</a> (09-May-2015)</p>
<ul dir="auto">
<li><a href="https://github.com/bbottema/simple-java-mail/issues/3" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/3/hovercard">#3</a>: turned off email regex validation by default, with the option to turn it back on</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/7" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/7/hovercard">#7</a>: fixed NullPointerException when using your own Session instance</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/10" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/10/hovercard">#10</a>: properly UTF-8 encode recipient addresses</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/14" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/14/hovercard">#14</a>: switched to <a href="https://www.slf4j.org/" rel="nofollow">SLF4J</a>, so you can easily use your own selected logging framework</li>
<li><a href="https://github.com/bbottema/simple-java-mail/issues/17" data-hovercard-type="issue" data-hovercard-url="/bbottema/simple-java-mail/issues/17/hovercard">#17</a>: Added <a href="https://en.wikipedia.org/wiki/Builder_pattern" rel="nofollow">fluent interface</a> for building emails (see <a href="https://www.simplejavamail.org/#section-builder-api" rel="nofollow">here</a> for an example)</li>
</ul>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.codemonkey.simplejavamail%7Csimple-java-mail%7C2.1%7Cjar" rel="nofollow">v2.1</a> (09-Aug-2012)</p>
<ul dir="auto">
<li>fixed character encoding for reply-to, from, to, body text and headers (to UTF-8)</li>
<li>fixed bug where Recipient was not public resulting in uncompilable code when calling email.getRecipients()</li>
</ul>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.codemonkey.simplejavamail%7Csimple-java-mail%7C2.0%7Cjar" rel="nofollow">v2.0</a> (20-Aug-2011)</p>
<ul dir="auto">
<li>added support for adding open headers, such as 'X-Priority: 2'</li>
</ul>
<p dir="auto"><a href="https://search.maven.org/#artifactdetails%7Corg.codemonkey.simplejavamail%7Csimple-java-mail%7C1.9.1%7Cjar" rel="nofollow">v1.9.1</a> (08-Aug-2011)</p>
<ul dir="auto">
<li>updated for Maven support</li>
</ul>
<p dir="auto">v1.9 (6-Aug-2011)</p>
<ul dir="auto">
<li>added support for JavaMail's reply-to address</li>
<li>made port optional as to support port defaulting based on protocol</li>
<li>added transport strategy default in the createSession method</li>
<li>tightened up thrown exceptions (MailException instead of RuntimeException)</li>
<li>added and fixed <a href="https://www.javadoc.io/doc/org.simplejavamail/simple-java-mail" rel="nofollow">Javadoc</a></li>
</ul>
<p dir="auto">v1.8</p>
<ul dir="auto">
<li>Added support for TLS (tested with gmail)</li>
</ul>
<p dir="auto">v1.7 (22-Mar-2011)</p>
<p dir="auto">Added support for SSL! (tested with gmail)</p>
<ul dir="auto">
<li>improved argument validation when creating a Mailer without preconfigured Session instance</li>
</ul>
<p dir="auto">known possible issue: SSL self-signed certificates might not work (yet). Please let me know by e-mail or create a new issue</p>
<p dir="auto">v1.6</p>
<p dir="auto">Completed migration to Java Simple Mail project.</p>
<ul dir="auto">
<li>removed all Vesijama references</li>
<li>updated TestMail demonstration class for clarification</li>
<li>updated readme.txt for test run instructions</li>
<li>included log4j.properties</li>
</ul>
<p dir="auto">v1.4 (15-Jan-2011)</p>
<p dir="auto">vX.X (26-Apr-2009)</p>
<ul dir="auto">
<li>Initial upload to Google Code.</li>
</ul>
</article>
  </div>

    </div>

  </readme-toc>

  

  <details class="details-reset details-overlay details-overlay-dark" id="jumpto-line-details-dialog">
    <summary data-hotkey="l" aria-label="Jump to line" role="button"></summary>
    <details-dialog class="Box Box--overlay d-flex flex-column anim-fade-in fast linejump overflow-hidden" aria-label="Jump to line" role="dialog" aria-modal="true">
      <!-- '"` --><!-- </textarea></xmp> --><form class="js-jump-to-line-form Box-body d-flex" data-turbo="false" action="" accept-charset="UTF-8" method="get">
        <input class="form-control flex-auto mr-3 linejump-input js-jump-to-line-field" type="text" placeholder="Jump to line…" aria-label="Jump to line" autofocus="">
          <button data-close-dialog="" type="submit" data-view-component="true" class="btn">    Go
</button>
</form>    </details-dialog>
  </details>



    <div class="pt-3">
      <details class="details-reset details-overlay details-overlay-dark ">
                <summary data-view-component="true" class="btn-link" role="button">    Give feedback
</summary>

  <details-dialog class="Box d-flex flex-column anim-fade-in fast Box--overlay overflow-visible" aria-label="Provide feedback" src="/bbottema/simple-java-mail/repos/code_nav_survey" role="dialog" aria-modal="true">
    <div class="Box-header">
      <button class="Box-btn-octicon btn-octicon float-right" type="button" aria-label="Close dialog" data-close-dialog="">
        <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-x">
    <path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path>
</svg>
      </button>
        <h1 class="Box-title">Provide feedback</h1>
    </div>
      <div class="Box-body overflow-auto">
                  <include-fragment>
            <svg style="box-sizing: content-box; color: var(--color-icon-primary);" width="32" height="32" viewBox="0 0 16 16" fill="none" data-view-component="true" class="my-3 mx-auto d-block anim-rotate">
  <circle cx="8" cy="8" r="7" stroke="currentColor" stroke-opacity="0.25" stroke-width="2" vector-effect="non-scaling-stroke"></circle>
  <path d="M15 8a7.002 7.002 0 00-7-7" stroke="currentColor" stroke-width="2" stroke-linecap="round" vector-effect="non-scaling-stroke"></path>
</svg>
          </include-fragment>

      </div>
  </details-dialog>
</details>
    </div>
</div>

  </div>


  </div>

</turbo-frame>


    </main>
  </div>

  </div>

          <footer class="footer width-full container-xl p-responsive" role="contentinfo">
  <h2 class="sr-only">Footer</h2>

  <div class="position-relative d-flex flex-items-center pb-2 f6 color-fg-muted border-top color-border-muted flex-column-reverse flex-lg-row flex-wrap flex-lg-nowrap mt-6 pt-6">
    <div class="list-style-none d-flex flex-wrap col-0 col-lg-2 flex-justify-start flex-lg-justify-between mb-2 mb-lg-0">
      <div class="mt-2 mt-lg-0 d-flex flex-items-center">
        <a aria-label="Homepage" title="GitHub" class="footer-octicon mr-2" href="https://github.com">
          <svg aria-hidden="true" height="24" viewBox="0 0 16 16" version="1.1" width="24" data-view-component="true" class="octicon octicon-mark-github">
    <path d="M8 0c4.42 0 8 3.58 8 8a8.013 8.013 0 0 1-5.45 7.59c-.4.08-.55-.17-.55-.38 0-.27.01-1.13.01-2.2 0-.75-.25-1.23-.54-1.48 1.78-.2 3.65-.88 3.65-3.95 0-.88-.31-1.59-.82-2.15.08-.2.36-1.02-.08-2.12 0 0-.67-.22-2.2.82-.64-.18-1.32-.27-2-.27-.68 0-1.36.09-2 .27-1.53-1.03-2.2-.82-2.2-.82-.44 1.1-.16 1.92-.08 2.12-.51.56-.82 1.28-.82 2.15 0 3.06 1.86 3.75 3.64 3.95-.23.2-.44.55-.51 1.07-.46.21-1.61.55-2.33-.66-.15-.24-.6-.83-1.23-.82-.67.01-.27.38.01.53.34.19.73.9.82 1.13.16.45.68 1.31 2.69.94 0 .67.01 1.3.01 1.49 0 .21-.15.45-.55.38A7.995 7.995 0 0 1 0 8c0-4.42 3.58-8 8-8Z"></path>
</svg>
</a>        <span>
        © 2023 GitHub, Inc.
        </span>
      </div>
    </div>

    <nav aria-label="Footer" class="col-12 col-lg-8">
      <h3 class="sr-only" id="sr-footer-heading">Footer navigation</h3>
      <ul class="list-style-none d-flex flex-wrap col-12 flex-justify-center flex-lg-justify-between mb-2 mb-lg-0" aria-labelledby="sr-footer-heading">
          <li class="mr-3 mr-lg-0"><a href="https://docs.github.com/site-policy/github-terms/github-terms-of-service" data-analytics-event="{&quot;category&quot;:&quot;Footer&quot;,&quot;action&quot;:&quot;go to terms&quot;,&quot;label&quot;:&quot;text:terms&quot;}">Terms</a></li>
          <li class="mr-3 mr-lg-0"><a href="https://docs.github.com/site-policy/privacy-policies/github-privacy-statement" data-analytics-event="{&quot;category&quot;:&quot;Footer&quot;,&quot;action&quot;:&quot;go to privacy&quot;,&quot;label&quot;:&quot;text:privacy&quot;}">Privacy</a></li>
          <li class="mr-3 mr-lg-0"><a data-analytics-event="{&quot;category&quot;:&quot;Footer&quot;,&quot;action&quot;:&quot;go to security&quot;,&quot;label&quot;:&quot;text:security&quot;}" href="https://github.com/security">Security</a></li>
          <li class="mr-3 mr-lg-0"><a href="https://www.githubstatus.com/" data-analytics-event="{&quot;category&quot;:&quot;Footer&quot;,&quot;action&quot;:&quot;go to status&quot;,&quot;label&quot;:&quot;text:status&quot;}">Status</a></li>
          <li class="mr-3 mr-lg-0"><a data-ga-click="Footer, go to help, text:Docs" href="https://docs.github.com">Docs</a></li>
          <li class="mr-3 mr-lg-0"><a href="https://support.github.com?tags=dotcom-footer" data-analytics-event="{&quot;category&quot;:&quot;Footer&quot;,&quot;action&quot;:&quot;go to contact&quot;,&quot;label&quot;:&quot;text:contact&quot;}">Contact GitHub</a></li>
          <li class="mr-3 mr-lg-0"><a href="https://github.com/pricing" data-analytics-event="{&quot;category&quot;:&quot;Footer&quot;,&quot;action&quot;:&quot;go to Pricing&quot;,&quot;label&quot;:&quot;text:Pricing&quot;}">Pricing</a></li>
        <li class="mr-3 mr-lg-0"><a href="https://docs.github.com" data-analytics-event="{&quot;category&quot;:&quot;Footer&quot;,&quot;action&quot;:&quot;go to api&quot;,&quot;label&quot;:&quot;text:api&quot;}">API</a></li>
        <li class="mr-3 mr-lg-0"><a href="https://services.github.com" data-analytics-event="{&quot;category&quot;:&quot;Footer&quot;,&quot;action&quot;:&quot;go to training&quot;,&quot;label&quot;:&quot;text:training&quot;}">Training</a></li>
          <li class="mr-3 mr-lg-0"><a href="https://github.blog" data-analytics-event="{&quot;category&quot;:&quot;Footer&quot;,&quot;action&quot;:&quot;go to blog&quot;,&quot;label&quot;:&quot;text:blog&quot;}">Blog</a></li>
          <li><a data-ga-click="Footer, go to about, text:about" href="https://github.com/about">About</a></li>
      </ul>
    </nav>
  </div>

  <div class="d-flex flex-justify-center pb-6">
    <span class="f6 color-fg-muted"></span>
  </div>
</footer>




  <div id="ajax-error-message" class="ajax-error-message flash flash-error" hidden="">
    <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-alert">
    <path d="M6.457 1.047c.659-1.234 2.427-1.234 3.086 0l6.082 11.378A1.75 1.75 0 0 1 14.082 15H1.918a1.75 1.75 0 0 1-1.543-2.575Zm1.763.707a.25.25 0 0 0-.44 0L1.698 13.132a.25.25 0 0 0 .22.368h12.164a.25.25 0 0 0 .22-.368Zm.53 3.996v2.5a.75.75 0 0 1-1.5 0v-2.5a.75.75 0 0 1 1.5 0ZM9 11a1 1 0 1 1-2 0 1 1 0 0 1 2 0Z"></path>
</svg>
    <button type="button" class="flash-close js-ajax-error-dismiss" aria-label="Dismiss error">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-x">
    <path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path>
</svg>
    </button>
    You can’t perform that action at this time.
  </div>

  <div class="js-stale-session-flash flash flash-warn flash-banner" hidden="">
    <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-alert">
    <path d="M6.457 1.047c.659-1.234 2.427-1.234 3.086 0l6.082 11.378A1.75 1.75 0 0 1 14.082 15H1.918a1.75 1.75 0 0 1-1.543-2.575Zm1.763.707a.25.25 0 0 0-.44 0L1.698 13.132a.25.25 0 0 0 .22.368h12.164a.25.25 0 0 0 .22-.368Zm.53 3.996v2.5a.75.75 0 0 1-1.5 0v-2.5a.75.75 0 0 1 1.5 0ZM9 11a1 1 0 1 1-2 0 1 1 0 0 1 2 0Z"></path>
</svg>
    <span class="js-stale-session-flash-signed-in" hidden="">You signed in with another tab or window. <a href="">Reload</a> to refresh your session.</span>
    <span class="js-stale-session-flash-signed-out" hidden="">You signed out in another tab or window. <a href="">Reload</a> to refresh your session.</span>
  </div>
    <template id="site-details-dialog">
  <details class="details-reset details-overlay details-overlay-dark lh-default color-fg-default hx_rsm" open="">
    <summary role="button" aria-label="Close dialog"></summary>
    <details-dialog class="Box Box--overlay d-flex flex-column anim-fade-in fast hx_rsm-dialog hx_rsm-modal">
      <button class="Box-btn-octicon m-0 btn-octicon position-absolute right-0 top-0" type="button" aria-label="Close dialog" data-close-dialog="">
        <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-x">
    <path d="M3.72 3.72a.75.75 0 0 1 1.06 0L8 6.94l3.22-3.22a.749.749 0 0 1 1.275.326.749.749 0 0 1-.215.734L9.06 8l3.22 3.22a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L8 9.06l-3.22 3.22a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L6.94 8 3.72 4.78a.75.75 0 0 1 0-1.06Z"></path>
</svg>
      </button>
      <div class="octocat-spinner my-6 js-details-dialog-spinner"></div>
    </details-dialog>
  </details>
</template>

    <div class="Popover js-hovercard-content position-absolute" style="display: none; outline: none;" tabindex="0">
  <div class="Popover-message Popover-message--bottom-left Popover-message--large Box color-shadow-large" style="width:360px;"></div>
</div>

    <template id="snippet-clipboard-copy-button">
  <div class="zeroclipboard-container position-absolute right-0 top-0">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn js-clipboard-copy m-2 p-0 tooltipped-no-delay" data-copy-feedback="Copied!" data-tooltip-direction="w">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon m-2">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none m-2">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div>
</template>


    <style>
      .user-mention[href$="/S230306"] {
        color: var(--color-user-mention-fg);
        background-color: var(--color-user-mention-bg);
        border-radius: 2px;
        margin-left: -2px;
        margin-right: -2px;
        padding: 0 2px;
      }
    </style>


    </div>

    <div id="js-global-screen-reader-notice" class="sr-only" aria-live="polite"></div>
  


<div id="crx-root"><div class="Gl1LytS7IKm0kbznepy9"><div></div></div></div></body></html>
