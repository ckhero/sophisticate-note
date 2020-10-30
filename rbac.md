# RBAC

> 1. 用户
>    1.     CREATE TABLE `admin_role_user` (
>             `admin_role_user_id` int(11) NOT NULL AUTO_INCREMENT,
>             `admin_role_user_admin_role_id` int(11) NOT NULL COMMENT '角色id',
>             `admin_role_user_admin_user_id` int(11) NOT NULL COMMENT '用户id',
>             `admin_role_use_create_at` datetime NOT NULL DEFAULT '1000-01-01 00:00:00',
>             `admin_role_use_update_at` timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
>             `admin_role_use_create_by` varchar(16) NOT NULL DEFAULT '',
>             `admin_role_use_update_by` varchar(16) NOT NULL DEFAULT '',
>             PRIMARY KEY (`admin_role_user_id`),
>             KEY `admin_role_user_idx1_idx` (`admin_role_user_admin_role_id`),
>             KEY `admin_role_user_idx2_idx` (`admin_role_user_admin_user_id`)
>           ) ENGINE=InnoDB AUTO_INCREMENT=453 DEFAULT CHARSET=utf8mb4 COMMENT='角色用户关联表';
> 2. 角色
>
>    1.     CREATE TABLE `admin_role` (
>             `admin_role_id` int(11) NOT NULL AUTO_INCREMENT COMMENT '角色id',
>             `admin_role_parent_id` int(11) NOT NULL DEFAULT '0' COMMENT '父角色id',
>             `admin_role_name` varchar(16) NOT NULL DEFAULT '' COMMENT '角色名称',
>             `admin_role_desc` varchar(255) NOT NULL DEFAULT '' COMMENT '角色描述',
>             `admin_role_status` tinyint(1) NOT NULL DEFAULT '0' COMMENT '状态 0-正常 1-停用',
>             `admin_role_type` tinyint(1) NOT NULL DEFAULT '0' COMMENT '类型 0-成员角色member 1-群组角色group',
>             `admin_role_create_at` datetime NOT NULL DEFAULT '1000-01-01 00:00:00' COMMENT '创建时间',
>             `admin_role_update_at` timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP COMMENT '更新时间',
>             `admin_role_create_by` varchar(16) NOT NULL DEFAULT '' COMMENT '创建人',
>             `admin_role_update_by` varchar(16) NOT NULL DEFAULT '' COMMENT '更新人',
>             PRIMARY KEY (`admin_role_id`),
>             UNIQUE KEY `admin_role_name_UNIQUE` (`admin_role_name`)
>           ) ENGINE=InnoDB AUTO_INCREMENT=10 DEFAULT CHARSET=utf8mb4 COMMENT='后台角色表'; 
>
> 3. 资源
>
>    1. > 、CREATE TABLE \`admin\_resource\` \(
>       >
>       >   \`admin\_resource\_id\` int\(11\) NOT NULL AUTO\_INCREMENT COMMENT '资源id',
>       >
>       >   \`admin\_resource\_parent\_id\` int\(11\) NOT NULL DEFAULT '0' COMMENT '资源父id',
>       >
>       >   \`admin\_resource\_type\` tinyint\(1\) NOT NULL DEFAULT '0' COMMENT '资源类型 0-菜单 1-功能',
>       >
>       >   \`admin\_resource\_target\` varchar\(64\) NOT NULL DEFAULT '' COMMENT '语义化索引',
>       >
>       >   \`admin\_resource\_data\` varchar\(1024\) NOT NULL DEFAULT '' COMMENT '资源data，json格式',
>       >
>       >   \`admin\_resource\_create\_at\` datetime NOT NULL DEFAULT '1000-01-01 00:00:00' COMMENT '创建时间',
>       >
>       >   \`admin\_resource\_update\_at\` timestamp NOT NULL DEFAULT CURRENT\_TIMESTAMP ON UPDATE CURRENT\_TIMESTAMP COMMENT '更新时间',
>       >
>       >   \`admin\_resource\_create\_by\` varchar\(16\) NOT NULL DEFAULT '' COMMENT '创建人',
>       >
>       >   \`admin\_resource\_update\_by\` varchar\(16\) NOT NULL DEFAULT '' COMMENT '更新人',
>       >
>       >   PRIMARY KEY \(\`admin\_resource\_id\`\),
>       >
>       >   KEY \`admin\_resource\_idx1\` \(\`admin\_resource\_parent\_id\`\),
>       >
>       >   KEY \`admin\_resource\_idx2\` \(\`admin\_resource\_target\`\)
>       >
>       > \) ENGINE=InnoDB AUTO\_INCREMENT=110 DEFAULT CHARSET=utf8mb4 COMMENT='资源表';
>
> 4. 权限
>
>    1. > CREATE TABLE \`admin\_privilege\` \(
>       >
>       >   \`admin\_privilege\_id\` int\(11\) NOT NULL AUTO\_INCREMENT COMMENT '权限id',
>       >
>       >   \`admin\_privilege\_admin\_resource\_id\` int\(11\) NOT NULL DEFAULT '0' COMMENT '资源id',
>       >
>       >   \`admin\_privilege\_admin\_role\_id\` int\(11\) NOT NULL DEFAULT '0' COMMENT '角色id',
>       >
>       >   \`admin\_privilege\_type\` varchar\(16\) NOT NULL DEFAULT '' COMMENT '权限类型 all-全部 access-访问 manage-管理',
>       >
>       >   \`admin\_privilege\_create\_at\` datetime NOT NULL DEFAULT '1000-01-01 00:00:00' COMMENT '创建时间',
>       >
>       >   \`admin\_privilege\_update\_at\` timestamp NOT NULL DEFAULT CURRENT\_TIMESTAMP ON UPDATE CURRENT\_TIMESTAMP COMMENT '更新时间',
>       >
>       >   \`admin\_privilege\_create\_by\` varchar\(16\) NOT NULL DEFAULT '' COMMENT '创建人',
>       >
>       >   \`admin\_privilege\_update\_by\` varchar\(16\) NOT NULL DEFAULT '' COMMENT '更新人',
>       >
>       >   PRIMARY KEY \(\`admin\_privilege\_id\`\),
>       >
>       >   KEY \`admin\_privilege\_resouce\_idx\` \(\`admin\_privilege\_admin\_resource\_id\`\),
>       >
>       >   KEY \`admin\_privilege\_role\_idx\` \(\`admin\_privilege\_admin\_role\_id\`\)
>       >
>       > \) ENGINE=InnoDB AUTO\_INCREMENT=488 DEFAULT CHARSET=utf8mb4 COMMENT='权限表';
>
> 5. 
> 6.



