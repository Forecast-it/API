# Person notification settings

Notifications can be dispatched to 4 different destinations:

- Email
- Inside the Forecast app
- Slack
- MSTeams.

Notification settings for each destination can be configured independently through configuration objects matching a shared interface: [topic_notification_settings](#topic-notification-settings).

## Get person notification settings

- `GET v1/persons/{personId}/notification_settings` - Returns all notification settings for a single person.

| Response fields                                       | Description/format                                          |
| ----------------------------------------------------- | ----------------------------------------------------------- |
| person_id                                             | Integer                                                     |
| project_deadline_notification_period                  | Integer                                                     |
| task_deadline_notification_period                     | Integer                                                     |
| invoice_notification_days_overdue                     | Integer                                                     |
| task_email_notification_frequency                     | String {"PUSH", "DAILY, "WEEKLY"}                           |
| notify_on_project_stage_change_only_assigned_projects | Boolean                                                     |
| notify_on_project_deadline_only_assigned_projects     | Boolean                                                     |
| notify_on_invoice_due_date_only_owned                 | Boolean                                                     |
| notify_on_invoice_overdue_only_owned                  | Boolean                                                     |
| notify_on_invoice_days_overdue_only_owned             | Boolean                                                     |
| notify_on_invoice_created_or_deleted_only_owned       | Boolean                                                     |
| notify_on_invoice_status_change_only_owned            | Boolean                                                     |
| notify_on_invoice_date_reached_only_owned             | Boolean                                                     |
| notify_on_invoice_payment_only_owned                  | Boolean                                                     |
| notify_on_invoice_date_changed_only_owned             | Boolean                                                     |
| notify_on_invoice_due_date_changed_only_owned         | Boolean                                                     |
| email_notification_settings                           | [topic_notification_settings](#topic-notification-settings) |
| in_app_notification_settings                          | [topic_notification_settings](#topic-notification-settings) |
| slack_notification_settings                           | [topic_notification_settings](#topic-notification-settings) |
| ms_teams_notification_settings                        | [topic_notification_settings](#topic-notification-settings) |

### Sample JSON request

`GET https://api.forecast.it/api/v1/persons/1/notification_settings`

### Sample JSON response

```javascript
{
    "person_id": 1,
    "project_deadline_notification_period": 10,
    "task_deadline_notification_period": 10,
    "invoice_notification_days_overdue": 15,
    "task_email_notification_frequency": "PUSH",
    "notify_on_project_stage_change_only_assigned_projects": false,
    "notify_on_project_deadline_only_assigned_projects": false,
    "notify_on_invoice_due_date_only_owned": false,
    "notify_on_invoice_overdue_only_owned": false,
    "notify_on_invoice_days_overdue_only_owned": false,
    "notify_on_invoice_created_or_deleted_only_owned": false,
    "notify_on_invoice_status_change_only_owned": false,
    "notify_on_invoice_date_reached_only_owned": false,
    "notify_on_invoice_payment_only_owned": false,
    "notify_on_invoice_date_changed_only_owned": false,
    "notify_on_invoice_due_date_changed_only_owned": false,
    "email_notification_settings": {
        "disable_notifications": false,
        "notify_on_project_status_change": false,
        "notify_on_assigned_project": false,
        "notify_on_person_join": false,
        "notify_on_project_deadline": false,
        "notify_on_task_deadline": false,
        "notify_on_assigned_task": false,
        "notify_on_assigned_task_update": false,
        "notify_on_mention": false,
        "notify_on_task_description_change": false,
        "notify_on_task_title_change": false,
        "notify_on_task_estimate_change": false,
        "notify_on_task_start_date_change": false,
        "notify_on_task_end_date_change": false,
        "notify_on_task_sprint_change": false,
        "notify_on_task_phase_change": false,
        "notify_on_task_status_column_change": false,
        "notify_on_task_project_change": false,
        "notify_on_task_subtask_change": false,
        "notify_on_task_subtask_estimate_change": false,
        "notify_on_task_comment_change": false,
        "notify_on_task_file_change": false,
        "notify_on_task_bug_change": false,
        "notify_on_task_blocked_change": false,
        "notify_on_task_repeating_change": false,
        "notify_on_invoice_due_date": false,
        "notify_on_invoice_overdue": false,
        "notify_on_invoice_days_overdue": false,
        "notify_on_invoice_created_or_deleted": false,
        "notify_on_invoice_status_change": false,
        "notify_on_invoice_date_reached": false,
        "notify_on_invoice_payment": false,
        "notify_on_invoice_date_changed": false,
        "notify_on_invoice_due_date_changed": false,
        "notify_on_time_off_manager": false,
        "notify_on_time_off_owner": false
    },
    "in_app_notification_settings": {
        "disable_notifications": false,
        "notify_on_project_status_change": false,
        "notify_on_assigned_project": false,
        "notify_on_person_join": false,
        "notify_on_project_deadline": false,
        "notify_on_task_deadline": false,
        "notify_on_assigned_task": false,
        "notify_on_assigned_task_update": false,
        "notify_on_mention": false,
        "notify_on_task_description_change": false,
        "notify_on_task_title_change": false,
        "notify_on_task_estimate_change": false,
        "notify_on_task_start_date_change": false,
        "notify_on_task_end_date_change": false,
        "notify_on_task_sprint_change": false,
        "notify_on_task_phase_change": false,
        "notify_on_task_status_column_change": false,
        "notify_on_task_project_change": false,
        "notify_on_task_subtask_change": false,
        "notify_on_task_subtask_estimate_change": false,
        "notify_on_task_comment_change": false,
        "notify_on_task_file_change": false,
        "notify_on_task_bug_change": false,
        "notify_on_task_blocked_change": false,
        "notify_on_task_repeating_change": false,
        "notify_on_invoice_due_date": false,
        "notify_on_invoice_overdue": false,
        "notify_on_invoice_days_overdue": false,
        "notify_on_invoice_created_or_deleted": false,
        "notify_on_invoice_status_change": false,
        "notify_on_invoice_date_reached": false,
        "notify_on_invoice_payment": false,
        "notify_on_invoice_date_changed": false,
        "notify_on_invoice_due_date_changed": false,
        "notify_on_time_off_manager": false,
        "notify_on_time_off_owner": false
    },
    "slack_notification_settings": {
        "disable_notifications": false,
        "notify_on_project_status_change": false,
        "notify_on_assigned_project": false,
        "notify_on_person_join": false,
        "notify_on_project_deadline": false,
        "notify_on_task_deadline": false,
        "notify_on_assigned_task": false,
        "notify_on_assigned_task_update": false,
        "notify_on_mention": false,
        "notify_on_task_description_change": false,
        "notify_on_task_title_change": false,
        "notify_on_task_estimate_change": false,
        "notify_on_task_start_date_change": false,
        "notify_on_task_end_date_change": false,
        "notify_on_task_sprint_change": false,
        "notify_on_task_phase_change": false,
        "notify_on_task_status_column_change": false,
        "notify_on_task_project_change": false,
        "notify_on_task_subtask_change": false,
        "notify_on_task_subtask_estimate_change": false,
        "notify_on_task_comment_change": false,
        "notify_on_task_file_change": false,
        "notify_on_task_bug_change": false,
        "notify_on_task_blocked_change": false,
        "notify_on_task_repeating_change": false,
        "notify_on_invoice_due_date": false,
        "notify_on_invoice_overdue": false,
        "notify_on_invoice_days_overdue": false,
        "notify_on_invoice_created_or_deleted": false,
        "notify_on_invoice_status_change": false,
        "notify_on_invoice_date_reached": false,
        "notify_on_invoice_payment": false,
        "notify_on_invoice_date_changed": false,
        "notify_on_invoice_due_date_changed": false,
        "notify_on_time_off_manager": false,
        "notify_on_time_off_owner": false
    },
    "ms_teams_notification_settings": {
        "disable_notifications": false,
        "notify_on_project_status_change": false,
        "notify_on_assigned_project": false,
        "notify_on_person_join": false,
        "notify_on_project_deadline": false,
        "notify_on_task_deadline": false,
        "notify_on_assigned_task": false,
        "notify_on_assigned_task_update": false,
        "notify_on_mention": false,
        "notify_on_task_description_change": false,
        "notify_on_task_title_change": false,
        "notify_on_task_estimate_change": false,
        "notify_on_task_start_date_change": false,
        "notify_on_task_end_date_change": false,
        "notify_on_task_sprint_change": false,
        "notify_on_task_phase_change": false,
        "notify_on_task_status_column_change": false,
        "notify_on_task_project_change": false,
        "notify_on_task_subtask_change": false,
        "notify_on_task_subtask_estimate_change": false,
        "notify_on_task_comment_change": false,
        "notify_on_task_file_change": false,
        "notify_on_task_bug_change": false,
        "notify_on_task_blocked_change": false,
        "notify_on_task_repeating_change": false,
        "notify_on_invoice_due_date": false,
        "notify_on_invoice_overdue": false,
        "notify_on_invoice_days_overdue": false,
        "notify_on_invoice_created_or_deleted": false,
        "notify_on_invoice_status_change": false,
        "notify_on_invoice_date_reached": false,
        "notify_on_invoice_payment": false,
        "notify_on_invoice_date_changed": false,
        "notify_on_invoice_due_date_changed": false,
        "notify_on_time_off_manager": false,
        "notify_on_time_off_owner": false
    }
}
```

## Update person notification settings

- `PUT v1/persons/{personId}/notification_settings`
  Updates notification settings for a single person. Returns the same response as getting notification settings for a single person.

| Request fields                                        | Description/format                                          |
| ----------------------------------------------------- | ----------------------------------------------------------- |
| person_id                                             | Integer                                                     |
| project_deadline_notification_period                  | Integer                                                     |
| task_deadline_notification_period                     | Integer                                                     |
| invoice_notification_days_overdue                     | Integer                                                     |
| task_email_notification_frequency                     | String {"PUSH", "DAILY, "WEEKLY"}                           |
| notify_on_project_stage_change_only_assigned_projects | Boolean                                                     |
| notify_on_project_deadline_only_assigned_projects     | Boolean                                                     |
| notify_on_invoice_due_date_only_owned                 | Boolean                                                     |
| notify_on_invoice_overdue_only_owned                  | Boolean                                                     |
| notify_on_invoice_days_overdue_only_owned             | Boolean                                                     |
| notify_on_invoice_created_or_deleted_only_owned       | Boolean                                                     |
| notify_on_invoice_status_change_only_owned            | Boolean                                                     |
| notify_on_invoice_date_reached_only_owned             | Boolean                                                     |
| notify_on_invoice_payment_only_owned                  | Boolean                                                     |
| notify_on_invoice_date_changed_only_owned             | Boolean                                                     |
| notify_on_invoice_due_date_changed_only_owned         | Boolean                                                     |
| email_notification_settings                           | [topic_notification_settings](#topic-notification-settings) |
| in_app_notification_settings                          | [topic_notification_settings](#topic-notification-settings) |
| slack_notification_settings                           | [topic_notification_settings](#topic-notification-settings) |
| ms_teams_notification_settings                        | [topic_notification_settings](#topic-notification-settings) |

### Sample JSON request

PUT https://api.forecast.it/api/v1/persons/1/notification_settings

```javascript
{
    "project_deadline_notification_period": 10,
    "task_email_notification_frequency": "WEEKLY",
    "notify_on_project_stage_change_only_assigned_projects": false,
    "notify_on_invoice_date_changed_only_owned": false,
    "email_notification_settings": {
        "disable_notifications": false,
        "notify_on_task_subtask_change": true,
        "notify_on_task_subtask_estimate_change": true,
        "notify_on_task_comment_change": true,
        "notify_on_task_file_change": false,
        "notify_on_invoice_payment": true,
        "notify_on_invoice_date_changed": false,
        "notify_on_invoice_due_date_changed": true,
        "notify_on_time_off_manager": true,
        "notify_on_time_off_owner": false
    },
    "in_app_notification_settings": {
        "notify_on_mention": true,
        "notify_on_task_description_change": true,
        "notify_on_task_status_column_change": false,
    },
    "slack_notification_settings": {
        "disable_notifications": false,
        "notify_on_assigned_project": true,
        "notify_on_assigned_task": true,
        "notify_on_assigned_task_update": false,
        "notify_on_mention": true,
        "notify_on_time_off_owner": true
    },
    "ms_teams_notification_settings": {
        "disable_notifications": true,
        "notify_on_time_off_manager": true,
        "notify_on_time_off_owner": false
    }
}
```

## Topic notification settings

- Shape of generic `topic_notification_settings` object.

| Request / Response fields              | Description/ format |
| -------------------------------------- | ------------------- |
| disable_notifications                  | Boolean\*           |
| notify_on_project_status_change        | Boolean             |
| notify_on_assigned_project             | Boolean             |
| notify_on_person_join                  | Boolean             |
| notify_on_project_deadline             | Boolean             |
| notify_on_task_deadline                | Boolean             |
| notify_on_assigned_task                | Boolean             |
| notify_on_assigned_task_update         | Boolean             |
| notify_on_mention                      | Boolean             |
| notify_on_task_description_change      | Boolean             |
| notify_on_task_title_change            | Boolean             |
| notify_on_task_estimate_change         | Boolean             |
| notify_on_task_start_date_change       | Boolean             |
| notify_on_task_end_date_change         | Boolean             |
| notify_on_task_sprint_change           | Boolean             |
| notify_on_task_phase_change            | Boolean             |
| notify_on_task_status_column_change    | Boolean             |
| notify_on_task_project_change          | Boolean             |
| notify_on_task_subtask_change          | Boolean             |
| notify_on_task_subtask_estimate_change | Boolean             |
| notify_on_task_comment_change          | Boolean             |
| notify_on_task_file_change             | Boolean             |
| notify_on_task_bug_change              | Boolean             |
| notify_on_task_blocked_change          | Boolean             |
| notify_on_task_repeating_change        | Boolean             |
| notify_on_invoice_due_date             | Boolean             |
| notify_on_invoice_overdue              | Boolean             |
| notify_on_invoice_days_overdue         | Boolean             |
| notify_on_invoice_created_or_deleted   | Boolean             |
| notify_on_invoice_status_change        | Boolean             |
| notify_on_invoice_date_reached         | Boolean             |
| notify_on_invoice_payment              | Boolean             |
| notify_on_invoice_date_changed         | Boolean             |
| notify_on_invoice_due_date_changed     | Boolean             |
| notify_on_time_off_manager             | Boolean             |
| notify_on_time_off_owner               | Boolean             |

\* Setting the `disable_notifications` option to `true` will prevent all notifications on the topic from being sent for as long as it remains `true`, but will not otherwise overwrite the person's settings. This means that you can configure what a person's notification settings should be without needing to turn the notifications on at the same time.
