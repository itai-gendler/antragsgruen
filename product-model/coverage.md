---
{
  "scope": "Inspected core consultation, document, participation, procedure, assembly, account and administration slices.",
  "method": "Static tracing of entry points, handlers, persistence and authorization, with documentation as context.",
  "covered": [
    {
      "description": "Core route and consultation access handlers.",
      "paths": [
        "config/urls.php",
        "controllers/Base.php",
        "controllers/rest/RestBase.php",
        "controllers/admin/AdminBase.php",
        "components/ConsultationAccess.php"
      ]
    },
    {
      "description": "Document lifecycle, discussion, procedure and administration handlers and associated models.",
      "paths": [
        "controllers/MotionController.php",
        "controllers/AmendmentController.php",
        "controllers/MotionActionsTrait.php",
        "controllers/AmendmentActionsTrait.php",
        "controllers/admin/MotionController.php",
        "controllers/admin/AmendmentController.php",
        "controllers/admin/MotionListController.php",
        "controllers/admin/ProposedProcedureController.php",
        "models/db/IMotion.php",
        "models/db/Motion.php",
        "models/db/Amendment.php",
        "models/db/IProposal.php",
        "models/db/MotionProposal.php",
        "models/db/AmendmentProposal.php",
        "models/db/ISupporter.php",
        "models/db/IComment.php",
        "models/forms/MotionEditForm.php",
        "models/forms/AmendmentEditForm.php",
        "models/forms/ProposedChangeForm.php",
        "models/settings/Permissions.php",
        "models/forms/CommentForm.php",
        "models/api/imotion/MotionDetails.php",
        "models/api/imotion/AmendmentDetails.php",
        "models/api/imotion/Supporter.php",
        "models/api/proposedprocedure/MotionProposedProcedure.php",
        "models/api/proposedprocedure/AmendmentProposedProcedure.php",
        "views/motion/view.php",
        "views/amendment/view.php",
        "views/shared/_proposed_procedure_log.php"
      ]
    },
    {
      "description": "Single and assembly merging handlers, saved-data models and interaction code.",
      "paths": [
        "controllers/AmendmentMergingTrait.php",
        "controllers/MotionMergingTrait.php",
        "models/mergeAmendments/",
        "models/forms/MergeSingleAmendmentForm.php",
        "web/js/modules/frontend/MotionMergeAmendments.js",
        "web/js/modules/shared/MotionMergeChangeActions.js"
      ]
    },
    {
      "description": "Inspected voting, speaking and debate handlers, projections and persistence.",
      "paths": [
        "controllers/rest/VotingController.php",
        "controllers/rest/SpeechController.php",
        "controllers/rest/DebateController.php",
        "controllers/VotingController.php",
        "components/VotingMethods.php",
        "components/DebateTools.php",
        "models/db/VotingBlock.php",
        "models/settings/VotingBlock.php",
        "models/api/voting/VotingPayloadBuilder.php",
        "models/db/SpeechQueue.php",
        "models/db/SpeechQueueItem.php",
        "models/db/DebateItem.php",
        "views/voting/admin-download-results.php"
      ]
    },
    {
      "description": "Inspected account, preference, membership, scoped grant and import code.",
      "paths": [
        "controllers/UserController.php",
        "controllers/rest/UserController.php",
        "controllers/admin/UsersController.php",
        "models/forms/LoginUsernamePasswordForm.php",
        "models/db/User.php",
        "models/db/UserNotification.php",
        "components/UserGroupAdminMethods.php",
        "models/settings/UserGroupPermissionEntry.php",
        "components/SecondFactorAuthentication.php",
        "models/settings/User.php",
        "models/settings/UserGroupPermissions.php",
        "views/user/my_account.php"
      ]
    },
    {
      "description": "Inspected consultation, type, agenda, wording, page, uploaded-file and document-export code.",
      "paths": [
        "controllers/admin/IndexController.php",
        "controllers/admin/MotionTypeController.php",
        "controllers/admin/AgendaController.php",
        "controllers/PagesController.php",
        "controllers/MotionExportTraits.php",
        "models/db/Consultation.php",
        "models/db/ConsultationMotionType.php",
        "models/db/ConsultationSettingsMotionSection.php",
        "models/db/ConsultationAgendaItem.php",
        "models/db/ConsultationSettingsTag.php",
        "models/db/ConsultationText.php",
        "models/db/ConsultationFile.php",
        "models/db/ConsultationFileGroup.php",
        "controllers/rest/MotionTypeController.php",
        "models/api/motionType/MotionTypeUpdateRequest.php",
        "views/motion/LayoutHelper.php",
        "views/amendment/LayoutHelper.php",
        "views/motion/plain_html.php"
      ]
    }
  ],
  "exclusions": [
    {
      "description": "Executable build, deployment, migration and test machinery and visual assets.",
      "paths": [
        "docker/",
        "migrations/",
        "tests/",
        "assets/",
        "web/css/",
        ".github/"
      ]
    }
  ],
  "unmapped": [
    {
      "description": "Plugin contracts, external providers, active generation and specialist integrations.",
      "paths": [
        "plugins/"
      ]
    },
    {
      "description": "Installation, hosting, manager, provisioning, updater and synchronization handlers.",
      "paths": [
        "controllers/InstallationController.php",
        "controllers/ManagerController.php",
        "commands/"
      ]
    },
    {
      "description": "Document move/copy, specialist applications, nontext sections and remaining export behavior.",
      "paths": [
        "models/forms/MotionMover.php",
        "models/forms/MotionDeepCopy.php",
        "models/sectionTypes/",
        "components/latex/"
      ]
    },
    {
      "description": "Unsubscribe/blocklist, remaining REST operations and live transport behavior.",
      "paths": [
        "controllers/UserController.php",
        "controllers/rest/",
        "components/LiveDataChannels.php"
      ]
    }
  ],
  "limitations": [
    {
      "description": "Anonymous account projection passes null to a required object response parameter.",
      "paths": [
        "controllers/rest/UserController.php",
        "controllers/rest/RestBase.php"
      ]
    },
    {
      "description": "Declared Amendment creation/document updates lack corresponding core routes; Agenda uses a different implemented session access contract.",
      "paths": [
        "docs/openapi.yaml",
        "controllers/rest/AmendmentController.php",
        "controllers/rest/MotionController.php",
        "controllers/admin/AgendaController.php"
      ]
    },
    {
      "description": "Dependent text-rewrite failure returns false without saveMotion propagating a save error; valid administrative details and earlier effects can still persist.",
      "paths": [
        "models/forms/MotionEditForm.php",
        "controllers/admin/MotionController.php"
      ]
    },
    {
      "description": "Forced factor enrollment hides the personal removal control, while the submitted save handler does not repeat that condition before removing a matching key.",
      "paths": [
        "controllers/UserController.php",
        "components/SecondFactorAuthentication.php",
        "views/user/my_account.php"
      ]
    }
  ]
}
---

# Coverage
